Currently looking for help with those things:

**Community**
- If you have experience with Dear ImGui and programming, helping people out on the [Discourse forum](http://discourse.dearimgui.org/) would be very useful.
- The wiki needs improvements!

**Features**
- Viewport: The multi-viewport branch needs users/testers to move forward! (see Viewport branch and [#1542](https://github.com/ocornut/imgui/issues/1542)). In particular, things may not work as well on all back-ends or operating systems (Linux/OSX are poorly tested regardless of the underlying back-end).

**Platform/Renderer Bindings**
- Mac: imgui_impl_osx.mm need some love ([#1873](https://github.com/ocornut/imgui/issues/1873))
- SDL: Added game controller support for navigation in imgui_impl_sdl.cpp (model it on gamepad code from imgui_impl_glfw.cpp)
- Mobile, Web: Wanted: Make sure the existing OpenGL renderers are compatible with whatever WebGL / GL ES versions those platform needs, or write separate renderers if needed.
- Mobile: Wanted imgui_impl_ios.cpp Platform Binding+Example for iOS (+ use existing renderer).
- Mobile: Wanted imgui_impl_android.cpp Platform Binding+Example for Android (+ use existing renderer).
- Web: Wanted imgui_impl_emscripten.cpp Platform Binding+Example for Emscripten (+ use existing renderer to create a new example). ([#336](https://github.com/ocornut/imgui/pull/336))
- Viewport: DirectX12 bindings needs multi-viewport support (see Viewport branch and [#1542](https://github.com/ocornut/imgui/issues/1542)).
- Viewport: Vulkan bindings needs to fix multi-viewport support (see Viewport branch and [#1542](https://github.com/ocornut/imgui/issues/1542)): currently has Present issues.

**External Language Bindings**
- Many language bindings are not kept up to date (see https://github.com/ocornut/imgui/wiki/Links)
- Help with the work on a binding generator. See the work in [#1879](https://github.com/ocornut/imgui/issues/1879), feedback/help welcome. Ideally this would lead us toward officially maintained C bindings.

**Third-party Software**
<br>If you are familiar or interested in GLFW pushing/developing those changes would be extremely helpful to imgui:
- GLFW: implement/solve https://github.com/glfw/glfw/issues/427 in GLFW to add missing diagonal resize mouse cursors.
- GLFW: implement/solve https://github.com/glfw/glfw/issues/1236 in GLFW to allow for portable multi-viewport support.
- GLFW: implement/solve https://github.com/glfw/glfw/pull/989 in GLFW to allow for portable multi-viewport support. (Update: PR submitted as https://github.com/glfw/glfw/pull/1322)
