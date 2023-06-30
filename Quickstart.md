The [examples/](https://github.com/ocornut/imgui/tree/master/examples) folder is populated with applications demonstrating Dear ImGui with variety of common windowing and graphics API. There were designed to be as straightforward possible. However in most cases, a majority of the example code is related to setting up the windowing and graphics API (aka setting up a basic application) rather than setting up Dear ImGui itself. 

If you have issues integrating Dear ImGui in your app, most of the time to easiest thing to do it refer to those [examples](https://github.com/ocornut/imgui/tree/master/examples).

## Compiling/Linking

- (1) Pull the repository into a submodule of your project, or simply download/copy the repository in yours and commit it.
- (2) Add `imgui/{*.cpp,*.h}` to your project or build system of your choice, so they get compiled and linked in your app.
- (3) Add `imgui/backends/imgui_impl_xxxx{.cpp,.h}` files corresponding to the technology you use from the `imgui/backends/` folder (e.g. if your app uses SDL2 + DirectX11, add `imgui_impl_sdl2.cpp`, `imgui_impl_dx11.cpp` etc.).
- (4) Optionally add to your project: `misc/debugger/imgui.natvis` (Visual Studio users), `misc/cpp/imgui_stdlib.*` (std::string users).

**If your application already uses the API you pulled the backends for, things should compile and link already.**

Most users having linking problems are in fact having problems because of the underlying windowing or graphics tech they use. e.g. If you use DirectX11 you need to link with d3d11.lib, if you use SDL2 you need to obtain the library (from their website or vcpkg) and link with SDL2.lib+SDL2main.lib etc. 
If you already have an app running by definition you shouldn't have this problem. If you are creating a new application: while it is generally outside of scope of Dear ImGui to document how to use a million windowing/graphics stacks, you can refer to our [examples/](https://github.com/ocornut/imgui/tree/master/examples) folder to see which libs/settings we are using. For the convenience of providing easy-to-compile examples, for years our repository has included an (old) precompiled version of GLFW 3.2 for Windows.

## Setting up Dear ImGui & Backends

- (1) Include header files for main lib (`#include "imgui.h") + backends (e.g. `#include "imgui_impl_win32.h"`, `#include "imgui_impl_dx11.h"`).
- (2) Create Dear ImGui context with `ImGui::CreateContext()`.
- (3) Optionally set configuration flags, load fonts, setup style.
- (4) Initialize Platform and Rendering backends (e.g. `ImGui_ImplWin32_Init()` + `ImGui_ImplDX11_Init()`).
- (5) Start of main loop: call backends' NewFrame functions + call `ImGui::NewFrame()`.
- (6) End of main loop: call `ImGui::Render()` + call Render function of Rendering backend.
- (7) Most backends requires extra steps to hook or forward events.
- (8) Shutdown backends, destroy Dear ImGui context with `ImGui::DestroyContext()`.

## Example: Using Win32 + DirectX11

Full standalone example: [example_win32_directx11/main.cpp](https://github.com/ocornut/imgui/blob/master/examples/example_win32_directx11/main.cpp)

Add to Includes:
```cpp
// Includes
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
// Start the Dear ImGui frame
ImGui_ImplDX11_NewFrame();
ImGui_ImplWin32_NewFrame();
ImGui::NewFrame();
ImGui::ShowDemoWindow(); // Show demo window :)
```
Add to end of main loop:
```cpp
// Rendering
ImGui::Render();
ImGui_ImplDX11_RenderDrawData(ImGui::GetDrawData());
```
Add to your WndProc handler:
```cpp
extern IMGUI_IMPL_API LRESULT ImGui_ImplWin32_WndProcHandler(HWND hWnd, UINT msg, WPARAM wParam, LPARAM lParam);
if (ImGui_ImplWin32_WndProcHandler(hWnd, msg, wParam, lParam))
    return true;
```
Add to Shutdown:
```cpp
ImGui_ImplDX11_Shutdown();
ImGui_ImplWin32_Shutdown();
ImGui::DestroyContext();
```