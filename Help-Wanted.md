Currently looking for help with those things.
<br>**This is absolutely not a complete list** (there a millions of other things to do, see [Issues](https://github.com/ocornut/imgui/issues) and [docs/TODO.txt](https://github.com/ocornut/imgui/blob/master/docs/TODO.txt)), those are merely some suggestions of things I am particularly struggling with before I may not have the hardware or expertise. If you are motivated and want to help this project and the community there is almost certainly a spot for you :)

**Community**
- If you have experience with Dear ImGui and programming, helping people out on the [Discourse forum](http://discourse.dearimgui.org/) would be very useful.
- Helping to answer in the GitHub [issues/threads](https://github.com/ocornut/imgui/issues) is very helpful too! 
- The wiki needs improvements!

**Third-party Software**
<br>If you are familiar or interested in GLFW, designing/developing/submitting those changes to GLFW would be extremely helpful to imgui:
- GLFW: implement/solve https://github.com/glfw/glfw/issues/427 in GLFW to add missing diagonal resize mouse cursors.
- GLFW: implement/solve https://github.com/glfw/glfw/issues/1236 in GLFW to allow for portable multi-viewport support.
- Linux/Mac: implement workaround, see https://github.com/ocornut/imgui/issues/2117#issuecomment-465185644

**Features**
- Viewport: The multi-viewport feature needs users/testers to move forward! (see [#1542](https://github.com/ocornut/imgui/issues/1542), available in `docking` branch`). 
- Viewport: In particular, Linux/OSX have issues and need some work from volunteers. See [#2117](https://github.com/ocornut/imgui/issues/2117).
- Docking: See [#2109](https://github.com/ocornut/imgui/issues/2109).

**Platform/Renderer Bindings**
- Mac: imgui_impl_osx.mm need some love ([#1873](https://github.com/ocornut/imgui/issues/1873))
- SDL: Added game controller support for navigation in imgui_impl_sdl.cpp (model it on gamepad code from imgui_impl_glfw.cpp)
- Mobile, Web: Wanted: Make sure the existing OpenGL renderers are compatible with whatever WebGL / GL ES versions those platform needs, or write separate renderers if needed.
- Mobile: Wanted imgui_impl_ios.cpp Platform Binding+Example for iOS (+ use existing renderer).
- Mobile: Wanted imgui_impl_android.cpp Platform Binding+Example for Android (+ use existing renderer).
- Web: Wanted imgui_impl_emscripten.cpp Platform Binding+Example for Emscripten (+ use existing renderer to create a new example). ([#336](https://github.com/ocornut/imgui/pull/336))
- Viewport: DirectX12 bindings needs multi-viewport support (see Viewport branch and [#1542](https://github.com/ocornut/imgui/issues/1542)).
- Viewport: Vulkan bindings needs to fix multi-viewport support (see Viewport branch and [#1542](https://github.com/ocornut/imgui/issues/1542)): currently has Present issues.
- Viewport: Metal bindings needs multi-viewport support (see Viewport branch and [#1542](https://github.com/ocornut/imgui/issues/1542)).

**External Language Bindings**
- Many language bindings are not kept up to date (see https://github.com/ocornut/imgui/wiki/Links)
- Considering switching bindings to use the [cimgui](https://github.com/cimgui/cimgui) generated data so users of your framework/language can stay up to date without manual intervention.