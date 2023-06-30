The [examples/](https://github.com/ocornut/imgui/tree/master/examples) folder is populated with applications demonstrating Dear ImGui with variety of common windowing and graphics API. There were designed to be as straightforward possible. However in most cases, a majority of the example code is related to setting up the windowing and graphics API (aka setting up a basic application) rather than setting up Dear ImGui itself. 

If you have issues integrating Dear ImGui in your app, most of the time to easiest thing to do it refer to those [examples](https://github.com/ocornut/imgui/tree/master/examples).

## Index

- [Compiling/Linking](#compilinglinking)
- [Setting up Dear ImGui & Backends](#setting-up-dear-imgui--backends)
- [Example: If you are using Raw Win32 API + DirectX11](#example-if-you-are-using-raw-win32-api--directx11)
- [Example: If you are using Raw Win32 API + DirectX12](#example-if-you-are-using-raw-win32-api--directx12)
- [Example: If you are using GLFW + OpenGL/WebGL](#example-if-you-are-using-glfw--openglwebgl)
- [Example: If you are using GLFW + Metal (on Apple devices)](#example-if-you-are-using-glfw--metal-on-apple-devices)
- [Example: If you are using SDL2 + OpenGL/WebGL](#example-if-you-are-using-sdl2--openglwebgl)
- [Using another combination of backends?](#using-another-combination-of-backends)

## Compiling/Linking

- (1) Pull the repository into a submodule of your project, or simply download/copy the repository in yours and commit it.
- (2) Add `imgui/{*.cpp,*.h}` to your project or build system of your choice, so they get compiled and linked in your app.
- (3) Add `imgui/backends/imgui_impl_xxxx{.cpp,.h}` files corresponding to the technology you use from the `imgui/backends/` folder (e.g. if your app uses SDL2 + DirectX11, add `imgui_impl_sdl2.cpp`, `imgui_impl_dx11.cpp` etc.).
- (4) Optionally add to your project: `misc/debugger/imgui.natvis` (Visual Studio users), `misc/cpp/imgui_stdlib.*` (std::string users).

**If your application already uses the API you pulled the backends for, things should compile and link already.**

Most users having linking problems are in fact having problems because of the underlying windowing or graphics tech they use. e.g. If you use DirectX11 you need to link with d3d11.lib, if you use SDL2 you need to obtain the library (from their website or vcpkg) and link with SDL2.lib+SDL2main.lib etc. 
If you already have an app running by definition you shouldn't have this problem. If you are creating a new application: while it is generally outside of scope of Dear ImGui to document how to use a million windowing/graphics stacks, you can refer to our [examples/](https://github.com/ocornut/imgui/tree/master/examples) folder to see which libs/settings we are using. For the convenience of providing easy-to-compile examples, for years our repository has included an (old) precompiled version of GLFW 3.2 for Windows.

## Setting up Dear ImGui & Backends

- (1) Include header files for main lib (`#include "imgui.h"`) + backends (e.g. `#include "imgui_impl_win32.h"`, `#include "imgui_impl_dx11.h"`).
- (2) Create Dear ImGui context with `ImGui::CreateContext()`.
- (3) Optionally set configuration flags, load fonts, setup style.
- (4) Initialize Platform and Rendering backends (e.g. `ImGui_ImplWin32_Init()` + `ImGui_ImplDX11_Init()`).
- (5) Start of main loop: call backends' NewFrame functions + call `ImGui::NewFrame()`.
- (6) End of main loop: call `ImGui::Render()` + call Render function of Rendering backend.
- (7) Most backends requires extra steps to hook or forward events.
- (8) Shutdown backends, destroy Dear ImGui context with `ImGui::DestroyContext()`.
- (9) In your application input logic: you can poll `ImGui::GetIO().WantCaptureMouse`/`WantCaptureKeyboard` to tell if Dear ImGui wants to obstruct mouse/keyboard inputs from underlying apps. e.g. when hovering a window WantCaptureMouse will be set to true. One possible strategy there is to stop passing mouse events to your main application.

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
ImGui_ImplDX12_Init(YOUR_D3D_DEVICE, NUM_FRAME_IN_FLIGHT, YOUR_DXGI_FORMAT, 
 YOUR_SRV_DESC_HEAP, 
 YOUR_CPU_DESCRIPTOR_HANDLE_FOR_HEAP_START,
 YOUR_GPU_DESCRIPTOR_HANDLE_FOR_HEAP_START);
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

## Using another combination of backends?

The various examples above should reflect integration with a majority of backends, so you can follow the same logic.
Some backends require more information from you (e.g. in particular Vulkan and DirectX12 rendering backends). In doubt, refers to the corresponding [examples](https://github.com/ocornut/imgui/tree/master/examples) application.