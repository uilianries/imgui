## Quickstart

The [examples/](https://github.com/ocornut/imgui/tree/master/examples) folder is populated with applications demonstrating Dear ImGui with variety of common windowing and graphics API. There were designed to be as straightforward possible. However in most cases, a majority of the example code is related to setting up the windowing and graphics API (aka setting up a basic application) rather than setting up Dear ImGui itself. 

If you have issues integrating Dear ImGui in your app, most of the time to easiest thing to do it refer to those [examples](https://github.com/ocornut/imgui/tree/master/examples).

## Compiling/Linking

- (1) Pull the repository into a submodule of your project, or simply download/copy the repository in yours and commit it.
- (2) Add `imgui/{*.cpp,*.h}` to your project or build system of your choice, so they get compiled and linked in your app.
- (3) Add `imgui/backends/imgui_impl_xxxx{.cpp,.h}` files corresponding to the technology you use from the `imgui/backends/` folder (e.g. if your app uses SDL2 + DirectX11, add `imgui_impl_sdl2.cpp`, `imgui_impl_dx11.cpp` etc.).
- (4) Optionally add to your project: `misc/debugger/imgui.natvis` (Visual Studio users), `misc/cpp/imgui_stdlib.*` (std::string users).

If your application already uses the API you pulled the backends for, things should compile and link already.

Most users having linking problems when adding Dear ImGui are having problems because of the underlying windowing or graphics tech they use. e.g. If you use DirectX11 you need to link with d3d11.lib, if you use SDL2 you need to obtain the library (from their website or vcpkg) and link with SDL2.lib+SDL2main.lib etc. While it is generally outside of scope of Dear ImGui to document how to use a million windowing/graphics stacks, you can refer to our [examples/](https://github.com/ocornut/imgui/tree/master/examples) folder to see which libs/settings we are using. For the convenience of providing easy-to-compile examples, for years our repository has included an (old) precompiled version of GLFW 3.2 for Windows.

## Setting up Dear ImGui & Backends
