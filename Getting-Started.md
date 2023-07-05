## Index

- [Preamble](#preamble)
- [Compiling/Linking](#compilinglinking)
- [Setting up Dear ImGui & Backends](#setting-up-dear-imgui--backends)
- [Example: If you are using Raw Win32 API + DirectX11](#example-if-you-are-using-raw-win32-api--directx11)
- [Example: If you are using Raw Win32 API + DirectX12](#example-if-you-are-using-raw-win32-api--directx12)
- [Example: If you are using GLFW + OpenGL/WebGL](#example-if-you-are-using-glfw--openglwebgl)
- [Example: If you are using GLFW + Metal (on Apple devices)](#example-if-you-are-using-glfw--metal-on-apple-devices)
- [Example: If you are using SDL2 + OpenGL/WebGL](#example-if-you-are-using-sdl2--openglwebgl)
- [Example: If you are using SDL2 + Vulkan](#example-if-you-are-using-sdl2--vulkan)
- [Using another combination of backends?](#using-another-combination-of-backends)
- [Additional code to enable Multi-viewports mode](#additional-code-to-enable-multi-viewports-mode)

## Preamble 

**Build and run one of the examples application, play around with it.** 
<BR>With Visual Studio, open `examples/imgui_examples.sln`. XCode projects and Makefiles are also often provided.
<BR>You may not have all of the corresponding SDKs installed as we support many systems, but you should get some working out of the box.

The [examples/](https://github.com/ocornut/imgui/tree/master/examples) folder is populated with applications demonstrating Dear ImGui with a variety of common windowing and graphics API. They are designed to be as straightforward possible. However in most cases, a majority of the example-specific code is related to setting up the windowing and graphics API (aka setting up a basic application) rather than setting up Dear ImGui itself. 

If you have issues integrating Dear ImGui in your app, most of the time to easiest thing to do it refer to those [examples](https://github.com/ocornut/imgui/tree/master/examples).

For various reasons, our examples are very raw: we don't load fancy fonts and generally the Demo window cannot read anything from the filesystem, so our examples cannot showcase the use of e.g. texture.

## Compiling/Linking

- (1) Decide which branch to pull:
   - `master` or `docking`, the later adds support for [Docking](https://github.com/ocornut/imgui/wiki/Docking) and [Multi-viewports](https://github.com/ocornut/imgui/wiki/Multi-Viewports). 
   - Both branches are maintained, you can easily switch anytime.
- (2) Pull the repository into a submodule of your project, or simply download/copy the repository in yours and commit it.
- (3) Add files to your project or build system of your choice, so they get compiled and linked into your app.
   - Add all source files in the root folder: `imgui/{*.cpp,*.h}`.
   - Add selected `imgui/backends/imgui_impl_xxxx{.cpp,.h}` files corresponding to the technology you use from the `imgui/backends/` folder (e.g. if your app uses SDL2 + DirectX11, add `imgui_impl_sdl2.cpp`, `imgui_impl_dx11.cpp` etc.). If your engine uses multiple APIs you may include multiple backends.
   - Visual Studio users: Add `misc/debugger/imgui.natvis` and `misc/debugger/imgui.natstepfilter` to improve the debugging experience.
   - std::string users: Add `misc/cpp/imgui_stdlib.*` to easily use InputText with std::string.

**If your application already uses the API you pulled the backends for, things should compile and link already.**

Most users with linking problems are in fact having problems because of the underlying windowing or graphics tech they use. e.g. If you use DirectX11 you need to link with d3d11.lib, if you use SDL2 you need to obtain the library (from their website or vcpkg) and link with SDL2.lib+SDL2main.lib etc. 
If you already have an app running then by definition you shouldn't have a problem including corresponding header files and linking libraries.

If you are creating a new application from scratch: while it is generally outside of scope of Dear ImGui to document how to use every windowing/graphics stacks, you can refer to our [examples/](https://github.com/ocornut/imgui/tree/master/examples) folder to see which libs/settings we are using. Some people just copy our example to start a new testbed app. For the convenience of providing easy-to-compile examples, for years our repository has included an (old) precompiled version of GLFW 3.2 for Windows.

## Setting up Dear ImGui & Backends

After this list we will show the corresponding code.

- (1) Add `imgui/` to include paths. Include header files for main lib (`#include "imgui.h"`) + backends (e.g. `#include "imgui_impl_win32.h"`, `#include "imgui_impl_dx11.h"`).
- (2) Create Dear ImGui context with `ImGui::CreateContext()`.
- (3) Optionally set configuration flags, load fonts, setup style.
- (4) Initialize Platform and Rendering backends (e.g. `ImGui_ImplWin32_Init()` + `ImGui_ImplDX11_Init()`).
- (5) Start of main loop: call backends' ImGui_ImplXXX_NewFrame functions + call `ImGui::NewFrame()`.
- (6) End of main loop: call `ImGui::Render()` + call Render function of Rendering backend (e.g. `ImGui_ImplDX11_Render()`).
- (7) Most backends require some extra steps to hook or forward events. (e.g. calling `ImGui_ImplWin32_WndProcHandler`)
- (8) Call backend shutdown functions and destroy Dear ImGui context with `ImGui::DestroyContext()`.
- (9) In your application's input logic: you can poll `ImGui::GetIO().WantCaptureMouse`/`WantCaptureKeyboard` to check if Dear ImGui wants to obstruct mouse/keyboard inputs from underlying apps. e.g. when hovering a window `WantCaptureMouse` will be set to true, one possible strategy would be to stop passing mouse events to your main application.

## Example: If you are using Raw Win32 API + DirectX11

Full standalone example: [example_win32_directx11/main.cpp](https://github.com/ocornut/imgui/blob/master/examples/example_win32_directx11/main.cpp)

Add to Includes:
```cpp
#include "imgui.h"
#include "imgui_impl_win32.h"
#include "imgui_impl_dx11.h"
```
Add to Initialization:
```cpp
// Setup Dear ImGui context
IMGUI_CHECKVERSION();
ImGui::CreateContext();
ImGuiIO& io = ImGui::GetIO();
io.ConfigFlags |= ImGuiConfigFlags_NavEnableKeyboard;     // Enable Keyboard Controls
io.ConfigFlags |= ImGuiConfigFlags_NavEnableGamepad;      // Enable Gamepad Controls
io.ConfigFlags |= ImGuiConfigFlags_DockingEnable;         // IF using Docking Branch

// Setup Platform/Renderer backends
ImGui_ImplWin32_Init(YOUR_HWND);
ImGui_ImplDX11_Init(YOUR_D3D_DEVICE, YOUR_D3D_DEVICE_CONTEXT);
```
Add to start of main loop:
```cpp
// (Your code process and dispatch Win32 messages)
// Start the Dear ImGui frame
ImGui_ImplDX11_NewFrame();
ImGui_ImplWin32_NewFrame();
ImGui::NewFrame();
ImGui::ShowDemoWindow(); // Show demo window! :)
```
Add to end of main loop:
```cpp
// Rendering
// (Your code clears your framebuffer, renders your other stuff etc.)
ImGui::Render();
ImGui_ImplDX11_RenderDrawData(ImGui::GetDrawData());
// (Your code calls swapchain's Present() function)
```
Add to your WndProc handler:
```cpp
extern IMGUI_IMPL_API LRESULT ImGui_ImplWin32_WndProcHandler(HWND hWnd, UINT msg, WPARAM wParam, LPARAM lParam);
if (ImGui_ImplWin32_WndProcHandler(hWnd, msg, wParam, lParam))
    return true;
(Your code process Windows messages.)
```
Add to Shutdown:
```cpp
ImGui_ImplDX11_Shutdown();
ImGui_ImplWin32_Shutdown();
ImGui::DestroyContext();
```
That should be all!

## Example: If you are using Raw Win32 API + DirectX12

Full standalone example: [example_win32_directx12/main.cpp](https://github.com/ocornut/imgui/blob/master/examples/example_win32_directx12/main.cpp)

Add to Includes:
```cpp
#include "imgui.h"
#include "imgui_impl_win32.h"
#include "imgui_impl_dx12.h"
```
Add to Initialization:
```cpp
// Setup Dear ImGui context
IMGUI_CHECKVERSION();
ImGui::CreateContext();
ImGuiIO& io = ImGui::GetIO();
io.ConfigFlags |= ImGuiConfigFlags_NavEnableKeyboard;     // Enable Keyboard Controls
io.ConfigFlags |= ImGuiConfigFlags_NavEnableGamepad;      // Enable Gamepad Controls
io.ConfigFlags |= ImGuiConfigFlags_DockingEnable;         // IF using Docking Branch

// Setup Platform/Renderer backends
ImGui_ImplWin32_Init(YOUR_HWND);
ImGui_ImplDX12_Init(YOUR_D3D_DEVICE, NUM_FRAME_IN_FLIGHT, YOUR_RENDER_TARGET_DXGI_FORMAT, 
 YOUR_SRV_DESC_HEAP,
 // You'll need to designate a descriptor from your descriptor heap for Dear ImGui to use internally for its font texture's SRV
 YOUR_CPU_DESCRIPTOR_HANDLE_FOR_FONT_SRV,
 YOUR_GPU_DESCRIPTOR_HANDLE_FOR_FONT_SRV);
```
Add to start of main loop:
```cpp
// (Your code process and dispatch Win32 messages)
// Start the Dear ImGui frame
ImGui_ImplDX12_NewFrame();
ImGui_ImplWin32_NewFrame();
ImGui::NewFrame();
ImGui::ShowDemoWindow(); // Show demo window! :)
```
Add to end of main loop:
```cpp
// Rendering
// (Your code clears your framebuffer, renders your other stuff etc.)
ImGui::Render();
ImGui_ImplDX12_RenderDrawData(ImGui::GetDrawData(), YOUR_DX12_COMMAND_LIST);
// (Your code calls ExecuteCommandLists, swapchain's Present(), etc.)
```
Add to your WndProc handler:
```cpp
extern IMGUI_IMPL_API LRESULT ImGui_ImplWin32_WndProcHandler(HWND hWnd, UINT msg, WPARAM wParam, LPARAM lParam);
if (ImGui_ImplWin32_WndProcHandler(hWnd, msg, wParam, lParam))
    return true;
(Your code process Windows messages.)
```
Add to Shutdown:
```cpp
ImGui_ImplDX12_Shutdown();
ImGui_ImplWin32_Shutdown();
ImGui::DestroyContext();
```
That should be all!

## Example: If you are using GLFW + OpenGL/WebGL

Full standalone example: [example_glfw_opengl3/main.cpp](https://github.com/ocornut/imgui/blob/master/examples/example_glfw_opengl3/main.cpp)

Add to Includes:
```cpp
#include "imgui.h"
#include "imgui_impl_glfw.h"
#include "imgui_impl_opengl3.h"
```
Add to Initialization:
```cpp
// Setup Dear ImGui context
IMGUI_CHECKVERSION();
ImGui::CreateContext();
ImGuiIO& io = ImGui::GetIO();
io.ConfigFlags |= ImGuiConfigFlags_NavEnableKeyboard;     // Enable Keyboard Controls
io.ConfigFlags |= ImGuiConfigFlags_NavEnableGamepad;      // Enable Gamepad Controls
io.ConfigFlags |= ImGuiConfigFlags_DockingEnable;         // IF using Docking Branch

// Setup Platform/Renderer backends
ImGui_ImplGlfw_InitForOpenGL(YOUR_WINDOW, true);          // Second param install_callback=true will install GLFW callbacks and chain to existing ones.
ImGui_ImplOpenGL3_Init();
```
Add to start of main loop:
```cpp
// (Your code calls glfwPollEvents())
// ...
// Start the Dear ImGui frame
ImGui_ImplOpenGL3_NewFrame();
ImGui_ImplGlfw_NewFrame();
ImGui::NewFrame();
ImGui::ShowDemoWindow(); // Show demo window! :)
```
Add to end of main loop:
```cpp
// Rendering
// (Your code clears your framebuffer, renders your other stuff etc.)
ImGui::Render();
ImGui_ImplOpenGL3_RenderDrawData(ImGui::GetDrawData());
// (Your code calls glfwSwapBuffers() etc.)
```
Add to Shutdown:
```cpp
ImGui_ImplOpenGL3_Shutdown();
ImGui_ImplGlfw_Shutdown();
ImGui::DestroyContext();
```
That should be all!

## Example: If you are using GLFW + Metal (on Apple devices)

Full standalone example: [example_glfw_apple/main.mm](https://github.com/ocornut/imgui/blob/master/examples/example_glfw_apple/main.mm)

Add to Includes:
```cpp
#include "imgui.h"
#include "imgui_impl_glfw.h"
#include "imgui_impl_metal.h"
```
Add to Initialization:
```cpp
// Setup Dear ImGui context
IMGUI_CHECKVERSION();
ImGui::CreateContext();
ImGuiIO& io = ImGui::GetIO();
io.ConfigFlags |= ImGuiConfigFlags_NavEnableKeyboard;     // Enable Keyboard Controls
io.ConfigFlags |= ImGuiConfigFlags_NavEnableGamepad;      // Enable Gamepad Controls
io.ConfigFlags |= ImGuiConfigFlags_DockingEnable;         // IF using Docking Branch

// Setup Platform/Renderer backends
ImGui_ImplGlfw_InitForOpenGL(YOUR_WINDOW, true);          // Second param install_callback=true will install GLFW callbacks and chain to existing ones.
ImGui_ImplMetal_Init(YOUR_METAL_DEVICE);
```
Add to start of main loop:
```cpp
// (Your code calls glfwPollEvents())
// ...
// Start the Dear ImGui frame
ImGui_ImplMetal_NewFrame(YOUR_RENDER_PASS_DESCRIPTOR);
ImGui_ImplGlfw_NewFrame();
ImGui::NewFrame();
ImGui::ShowDemoWindow(); // Show demo window! :)
```
Add to end of main loop:
```cpp
// Rendering
// (Your code clears your framebuffer, renders your other stuff etc.)
ImGui::Render();
ImGui_ImplMetal_RenderDrawData(ImGui::GetDrawData(), YOUR_METAL_COMMAND_BUFFER, YOUR_METAL_RENDER_ENCODER);
// (Your code calls endEncoding, presentDrawable, commit etc.)
```
Add to Shutdown:
```cpp
ImGui_ImplMetal_Shutdown();
ImGui_ImplGlfw_Shutdown();
ImGui::DestroyContext();
```
That should be all!

## Example: If you are using SDL2 + OpenGL/WebGL

Full standalone example: [example_sdl2_opengl3/main.cpp](https://github.com/ocornut/imgui/blob/master/examples/example_sdl2_opengl3/main.cpp)

Add to Includes:
```cpp
#include "imgui.h"
#include "imgui_impl_sdl2.h"
#include "imgui_impl_opengl3.h"
```
Add to Initialization:
```cpp
// Setup Dear ImGui context
IMGUI_CHECKVERSION();
ImGui::CreateContext();
ImGuiIO& io = ImGui::GetIO();
io.ConfigFlags |= ImGuiConfigFlags_NavEnableKeyboard;     // Enable Keyboard Controls
io.ConfigFlags |= ImGuiConfigFlags_NavEnableGamepad;      // Enable Gamepad Controls
io.ConfigFlags |= ImGuiConfigFlags_DockingEnable;         // IF using Docking Branch

// Setup Platform/Renderer backends
ImGui_ImplSDL2_InitForOpenGL(window, YOUR_SDL_GL_CONTEXT);
ImGui_ImplOpenGL3_Init();
```
Add to start of main loop:
```cpp
// (Where your code calls SDL_PollEvent())
ImGui_ImplSDL2_ProcessEvent(&event); // Forward your event to backend

// (After event loop)
// Start the Dear ImGui frame
ImGui_ImplOpenGL3_NewFrame();
ImGui_ImplSDL2_NewFrame();
ImGui::NewFrame();
ImGui::ShowDemoWindow(); // Show demo window! :)
```
Add to end of main loop:
```cpp
// Rendering
// (Your code clears your framebuffer, renders your other stuff etc.)
ImGui::Render();
ImGui_ImplOpenGL3_RenderDrawData(ImGui::GetDrawData());
// (Your code calls SDL_GL_SwapWindow() etc.)
```
Add to Shutdown:
```cpp
ImGui_ImplOpenGL3_Shutdown();
ImGui_ImplSDL2_Shutdown();
ImGui::DestroyContext();
```
That should be all!

## Example: If you are using SDL2 + Vulkan

Full standalone example: [example_sdl2_vulkan/main.cpp](https://github.com/ocornut/imgui/blob/master/examples/example_sdl2_vulkan/main.cpp)

Unfortunately this is the most complex one and may not work with all app setups. We are always working on making imgui_impl_vulkan.cpp more compatible with existing engines, so please don't hesitate to post feedback.

Add to Includes:
```cpp
#include "imgui.h"
#include "imgui_impl_sdl2.h"
#include "imgui_impl_vulkan.h"

static void check_vk_result(VkResult err)
{
    if (err == 0)
        return;
    fprintf(stderr, "[vulkan] Error: VkResult = %d\n", err);
    if (err < 0)
        abort();
}
```
Add to Initialization:
```cpp
// Setup Dear ImGui context
IMGUI_CHECKVERSION();
ImGui::CreateContext();
ImGuiIO& io = ImGui::GetIO();
io.ConfigFlags |= ImGuiConfigFlags_NavEnableKeyboard;     // Enable Keyboard Controls
io.ConfigFlags |= ImGuiConfigFlags_NavEnableGamepad;      // Enable Gamepad Controls
io.ConfigFlags |= ImGuiConfigFlags_DockingEnable;         // IF using Docking Branch

// Setup Platform/Renderer backends
ImGui_ImplSDL2_InitForVulkan(YOUR_SDL_WINDOW);
ImGui_ImplVulkan_InitInfo init_info = {};
init_info.Instance = YOUR_INSTANCE;
init_info.PhysicalDevice = YOUR_PHYSICAL_DEVICE;
init_info.Device = YOUR_DEVICE;
init_info.QueueFamily = YOUR_QUEUE_FAMILY;
init_info.Queue = YOUR_QUEUE;
init_info.PipelineCache = YOUR_PIPELINE_CACHE;
init_info.DescriptorPool = YOUR_DESCRIPTOR_POOL;
init_info.Subpass = 0;
init_info.MinImageCount = 2;
init_info.ImageCount = 2;
init_info.MSAASamples = VK_SAMPLE_COUNT_1_BIT;
init_info.Allocator = YOUR_ALLOCATOR;
init_info.CheckVkResultFn = check_vk_result;
ImGui_ImplVulkan_Init(&init_info, wd->RenderPass);
// (this gets a bit more complicated, see example app for full reference)
ImGui_ImplVulkan_CreateFontsTexture(YOUR_COMMAND_BUFFER);
// (your code submit a queue)
ImGui_ImplVulkan_DestroyFontUploadObjects();
```
Add to start of main loop:
```cpp
// (Where your code calls SDL_PollEvent())
ImGui_ImplSDL2_ProcessEvent(&event); // Forward your event to backend

// (After event loop)
// Start the Dear ImGui frame
ImGui_ImplVulkan_NewFrame();
ImGui_ImplSDL2_NewFrame();
ImGui::NewFrame();
ImGui::ShowDemoWindow(); // Show demo window! :)
```
Add to end of main loop:
```cpp
// Rendering
// (Your code clears your framebuffer, renders your other stuff etc.)
ImGui::Render();
ImGui_ImplVulkan_RenderDrawData(ImGui::GetDrawData(), YOUR_COMMAND_BUFFER);
// (Your code calls vkCmdEndRenderPass, vkQueueSubmit, vkQueuePresentKHR etc.)
```
Add to Shutdown:
```cpp
ImGui_ImplVulkan_Shutdown();
ImGui_ImplSDL2_Shutdown();
ImGui::DestroyContext();
```
That should be all!

## Using another combination of backends?

The various examples above should reflect integration with a majority of backends, so you can follow the same logic.
Some backends require more information from you (e.g. in particular Vulkan and DirectX12 rendering backends). When in doubt, refer to the corresponding [examples](https://github.com/ocornut/imgui/tree/master/examples) application.

## Additional code to enable Multi-viewports mode

To use the [Multi-viewports](https://github.com/ocornut/imgui/wiki/Multi-Viewports) feature, pull the `docking` branch and enable the configuration flag:
```cpp
io.ConfigFlags |= ImGuiConfigFlags_ViewportsEnable; 
```
At the end of your render loop, generally after rendering your main viewport but before presenting/swapping it:
```cpp
// Update and Render additional Platform Windows
ImGui::UpdatePlatformWindows();
ImGui::RenderPlatformWindowsDefault();
```
