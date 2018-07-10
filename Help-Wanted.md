Currently looking for help with those things:

**Features**
- Viewport: The multi-viewport branch needs users/testers to move forward! (see Viewport branch and [#1542](https://github.com/ocornut/imgui/issues/1542))

**Platform/Renderer Bindings**
- Mac: imgui_impl_osx.mm need some love ([#1873](https://github.com/ocornut/imgui/issues/1873))
- Mobile, Web: Wanted: Make sure the existing OpenGL renderers are compatible with whatever WebGL / GL ES versions those platform needs, or write separate renderers if needed.
- Mobile: Wanted imgui_impl_ios.cpp Platform Binding+Example for iOS (+ use existing renderer).
- Mobile: Wanted imgui_impl_android.cpp Platform Binding+Example for Android (+ use existing renderer).
- Web: Wanted imgui_impl_emscripten.cpp Platform Binding+Example for Emscripten (+ use existing renderer to create a new example). ([#336](https://github.com/ocornut/imgui/pull/336))
- Viewport: DirectX12 bindings needs multi-viewport support (see Viewport branch and [#1542](https://github.com/ocornut/imgui/issues/1542)).
- Viewport: Vulkan bindings needs to fix multi-viewport support (see Viewport branch and [#1542](https://github.com/ocornut/imgui/issues/1542)): currently has Present issues.

**External Language Bindings**
- Many language bindings are not kept up to date (see https://github.com/ocornut/imgui/wiki/Links)
- Ideally, we could aim toward providing an official binding generator + an official C binding?

**Community**
- Help improving the wiki.
- Volunteers to moderate a Discourse forum dedicated to dear imgui.

**Third-party Software**
- GLFW: implement/solve https://github.com/glfw/glfw/issues/427 in GLFW to add missing diagonal resize mouse cursors.
- GLFW: implement/solve https://github.com/glfw/glfw/issues/1236 in GLFW to allow for portable multi-viewport support.
- GLFW: implement/solve https://github.com/glfw/glfw/pull/989 in GLFW to allow for portable multi-viewport support.
