This article will guide you through getting up and running with as many assumptions about your system as possible.

**You will learn**

- How to open a window using GLFW
- How to render an ImGui window into GLFW window
- How to render text into the ImGui window

**You are**

- On Linux
- Using C++11
- Using OpenGL 3.3 or above, core profile
- Using clang 3.4 or above
- Using glfw 3.0 or above

<br>
<br>
<br>

### Layout

This is the layout of your code.

```
| Directory           | Description
|---------------------|----------------------------------
| myproject/          |
|   build/            | Output goes here
|   include/          | Any include files you may eventually have
|   src/              |
|     main.cpp        | Your single source file
|   build.sh          | Your build script
```

<br>
<br>
<br>

### Build

Here is how your code will be built.

```bash
$ cd myproject
$ ./build.sh
```

**build.sh**

```bash
#!/usr/bin/env bash

mkdir -p build && \
pushd build && \
clang++ \
	-o main \
	../ext/imgui/imgui.cpp \
	../ext/imgui/imgui_draw.cpp \
	../src/main.cpp \
	-Wall \
	-g 						`# Generate complete debug info` \
	-std=c++11 \
	-I ../include \
	-I ../ext/glfw/include \
	-I ../ext/imgui \
	-L ../lib \
	-lglfw3 \
	-lGL \
	-lGLU \
	-lX11 \
	-lXxf86vm \
	-lXrandr \
	-lpthread \
	-lXi \
	-lXinerama \
  	-lXcursor && \
popd || exit 1
```

<br>
<br>
<br>

### Source

Here is the source.

**main.cpp**

```cpp
// dear imgui minimal example.

#include <cstdlib>
#include "GLFW/glfw3.h"
#include "imgui.h"

void setup(GLFWwindow* window);
void renderer(ImDrawData* draw_data);

int main(void)
{
    if (!glfwInit())
    {
        exit(EXIT_FAILURE);
    }

    static GLFWwindow* window {
        glfwCreateWindow(320, 240, "Simple example", NULL, NULL) 
    };

    if (!window)
    {
        glfwTerminate();
        exit(EXIT_FAILURE);
    }

    glfwMakeContextCurrent(window);

    // Close window on pressing ESC
    glfwSetKeyCallback(window, [](GLFWwindow* window, int key, int scancode, int action, int mods) {
        if (key == GLFW_KEY_ESCAPE && action == GLFW_PRESS)
            glfwSetWindowShouldClose(window, GL_TRUE);
    });

    setup(window);

    glClearColor(0.1f, 0.1f, 0.1f, 1.0f);
    while (!glfwWindowShouldClose(window))
    {
        glClear(GL_COLOR_BUFFER_BIT);

        glfwPollEvents();

        // Use ImGui functions between here and Render()
        ImGui::NewFrame();

        // This creates a window
        ImGui::Begin("Window Title Here");
        ImGui::Text("Hello, world!");
        ImGui::End();

        // ImGui functions end here
        ImGui::Render();

        glfwSwapBuffers(window);
    }

    glfwDestroyWindow(window);
    glfwTerminate();

    exit(EXIT_SUCCESS);
}

/*! /brief Initialise the ImGuiIO struct.
 *
 *   The ImGuiIO struct is the main configuration and
 *   I/O between your application and ImGui.
 */
void setup(GLFWwindow* window)
{
    unsigned char* pixels;
    int width,
        height,
        display_width,
        display_height;
    GLuint g_FontTexture;

    ImGuiIO& io { ImGui::GetIO() };

    io.Fonts->GetTexDataAsAlpha8(&pixels, &width, &height);

    // Upload texture to graphics system
    GLint last_texture;
    glGetIntegerv(GL_TEXTURE_BINDING_2D, &last_texture);
    glGenTextures(1, &g_FontTexture);
    glBindTexture(GL_TEXTURE_2D, g_FontTexture);
    glTexParameteri(GL_TEXTURE_2D, GL_TEXTURE_MIN_FILTER, GL_LINEAR);
    glTexParameteri(GL_TEXTURE_2D, GL_TEXTURE_MAG_FILTER, GL_LINEAR);
    glTexImage2D(GL_TEXTURE_2D, 0, GL_ALPHA, width, height, 0, GL_ALPHA, GL_UNSIGNED_BYTE, pixels);
    
    // Get display size
    glfwGetWindowSize(window, &width, &height);
    glfwGetFramebufferSize(window, &display_width, &display_height);

    io.DisplaySize = ImVec2((float)width, (float)height);
    io.RenderDrawListsFn = renderer;
    io.Fonts->TexID = (void *)(intptr_t)g_FontTexture;

    // Restore state
    glBindTexture(GL_TEXTURE_2D, last_texture);
}

/*! /brief Boilerplate function for OpenGL 2.0 rendering.
 *
 *  This function isn't written by us, but is mandatory
 *  boilerplate from the library. It can be copy/pasted
 *  into your projects, but should really be part of the
 *  library itself?
 */
void renderer(ImDrawData* draw_data)
{
    ImGuiIO& io { ImGui::GetIO() };
    int fb_width { (int)(io.DisplaySize.x * io.DisplayFramebufferScale.x) };
    int fb_height { (int)(io.DisplaySize.y * io.DisplayFramebufferScale.y) };

    draw_data->ScaleClipRects(io.DisplayFramebufferScale);

    GLint last_texture; glGetIntegerv(GL_TEXTURE_BINDING_2D, &last_texture);
    GLint last_viewport[4]; glGetIntegerv(GL_VIEWPORT, last_viewport);
    glPushAttrib(GL_ENABLE_BIT | GL_COLOR_BUFFER_BIT | GL_TRANSFORM_BIT);
    glEnable(GL_BLEND);
    glBlendFunc(GL_SRC_ALPHA, GL_ONE_MINUS_SRC_ALPHA);
    glDisable(GL_CULL_FACE);
    glDisable(GL_DEPTH_TEST);
    glEnable(GL_SCISSOR_TEST);
    glEnableClientState(GL_VERTEX_ARRAY);
    glEnableClientState(GL_TEXTURE_COORD_ARRAY);
    glEnableClientState(GL_COLOR_ARRAY);
    glEnable(GL_TEXTURE_2D);

    // Setup viewport, orthographic projection matrix
    glViewport(0, 0, (GLsizei)fb_width, (GLsizei)fb_height);
    glMatrixMode(GL_PROJECTION);
    glPushMatrix();
    glLoadIdentity();
    glOrtho(0.0f, io.DisplaySize.x, io.DisplaySize.y, 0.0f, -1.0f, +1.0f);
    glMatrixMode(GL_MODELVIEW);
    glPushMatrix();
    glLoadIdentity();

    // Render command lists
    #define OFFSETOF(TYPE, ELEMENT) ((size_t)&(((TYPE *)0)->ELEMENT))
    for (int n = 0; n < draw_data->CmdListsCount; n++)
    {
        const ImDrawList* cmd_list = draw_data->CmdLists[n];
        const unsigned char* vtx_buffer = (const unsigned char*)&cmd_list->VtxBuffer.front();
        const ImDrawIdx* idx_buffer = &cmd_list->IdxBuffer.front();
        glVertexPointer(2, GL_FLOAT, sizeof(ImDrawVert), (void*)(vtx_buffer + OFFSETOF(ImDrawVert, pos)));
        glTexCoordPointer(2, GL_FLOAT, sizeof(ImDrawVert), (void*)(vtx_buffer + OFFSETOF(ImDrawVert, uv)));
        glColorPointer(4, GL_UNSIGNED_BYTE, sizeof(ImDrawVert), (void*)(vtx_buffer + OFFSETOF(ImDrawVert, col)));

        for (int cmd_i = 0; cmd_i < cmd_list->CmdBuffer.size(); cmd_i++)
        {
            const ImDrawCmd* pcmd = &cmd_list->CmdBuffer[cmd_i];
            if (pcmd->UserCallback)
            {
                pcmd->UserCallback(cmd_list, pcmd);
            }
            else
            {
                glBindTexture(GL_TEXTURE_2D, (GLuint)(intptr_t)pcmd->TextureId);
                glScissor((int)pcmd->ClipRect.x, (int)(fb_height - pcmd->ClipRect.w), (int)(pcmd->ClipRect.z - pcmd->ClipRect.x), (int)(pcmd->ClipRect.w - pcmd->ClipRect.y));
                glDrawElements(GL_TRIANGLES, (GLsizei)pcmd->ElemCount, sizeof(ImDrawIdx) == 2 ? GL_UNSIGNED_SHORT : GL_UNSIGNED_INT, idx_buffer);
            }
            idx_buffer += pcmd->ElemCount;
        }
    }
    #undef OFFSETOF

    // Restore modified state
    glDisableClientState(GL_COLOR_ARRAY);
    glDisableClientState(GL_TEXTURE_COORD_ARRAY);
    glDisableClientState(GL_VERTEX_ARRAY);
    glBindTexture(GL_TEXTURE_2D, last_texture);
    glMatrixMode(GL_MODELVIEW);
    glPopMatrix();
    glMatrixMode(GL_PROJECTION);
    glPopMatrix();
    glPopAttrib();
    glViewport(last_viewport[0], last_viewport[1], (GLsizei)last_viewport[2], (GLsizei)last_viewport[3]);
}
```

<br>
<br>
<br>

#### TODO

Here are some ideas for how to improve and shorten this article.

- Add screenshot of result
- Reduce requirements, such as C++11
- Increase compatibility, such as including a cl.exe build script.
- Remove lines that aren't absolutely critical
- Remove `renderer()` - Seems unnecessary and better included with ImGui?
- Remove need to manually upload texture to GPU in `setup()`, can/should be included in ImGui?