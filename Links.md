### Language bindings

_NB: those bindings may be more or less maintained, more or less close to the spirit of original API. People who create language bindings sometimes haven't used the C++ API themselves. ImGui was designed for C++ and some of the subtleties may be lost in translation with other languages. If your language supports it, I would suggest replicating the function overloading and default parameters used in the original, else the API may be harder to use. In doubt, always check the original C++ version first!_

C (cimgui): thin c-api wrapper for ImGui
<br>https://github.com/Extrawurst/cimgui

C#/.Net (ImGui.NET): An ImGui wrapper for .NET Core
<br>https://github.com/mellinoe/ImGui.NET

ChaiScript (imgui-chaiscript): ChaiScript bindings for ImGui
<br>https://github.com/JuJuBoSc/imgui-chaiscript

CovScript (covscript-imgui): ImGui Extension for CovScript (Covariant)
<br>https://github.com/covscript/covscript-imgui

D (DerelictImgui): Dynamic bindings to the cimgui library for the D programming language
<br>https://github.com/Extrawurst/DerelictImgui

Go (go-imgui): Go bindings for the dear imgui immediate mode GUI library 
<br>https://github.com/Armored-Dragon/go-imgui

Haxe/hxcpp (linc_imgui): binding for imgui
<br>https://github.com/Aidan63/linc_imgui

JavaScript (imgui-js): JavaScript bindings for Dear ImGui using Emscripten and TypeScript
<br>https://github.com/flyover/imgui-js

Odin: Odin binding for Dear ImGui
<br>https://github.com/ThisDrunkDane/odin-dear_imgui

Python (CyImGui): Python bindings for ImGui using Cython.
<br>https://github.com/chromy/cyimgui

Python (pyimgui): Cython-based Python bindings for dear imgui
<br>https://github.com/swistakm/pyimgui

PureBasic (pb-cimgui): PureBasic interface to CImGui Wrapper
<br>https://github.com/hippyau/pb-cimgui

Rust (imgui-rs): Rust bindings for ImGui
<br>https://github.com/Gekkio/imgui-rs

Rust: "ImStr" Patch by @bitshifter to use string-range more commonly instead of zero-terminated strings.
<br>https://github.com/ocornut/imgui/pull/683

Lua: imgui bindings for lua (also see: LOVE binding)
<br>https://github.com/patrickriordan/imgui_lua_bindings

Lua: FFI bindings for LuaJIT
<br>https://github.com/thenumbernine/lua-ffi-bindings

Pascal (imgui-pas): pascal bindings for imgui
<br>https://github.com/dpethes/imgui-pas

### Port/rewrites

Java - JVM port, written in Kotlin, 100% Java compatible
<br>https://github.com/kotlin-graphics/imgui

### Framework/engine bindings

Main ImGui repository include examples for DirectX9, DirectX10, DirectX11, DirectX12, OpenGL2/3, Vulkan, Allegro 5, SDL+GL2/3, iOS and Marmalade.
<br>https://github.com/ocornut/imgui/tree/master/examples

- Unmerged PR: SDL2 + OpenGLES + Emscripten example: https://github.com/ocornut/imgui/pull/336
- Unmerged PR: SDL2 + Vulkan example: https://github.com/ocornut/imgui/pull/1367
- Unmerged PR: FreeGlut + OpenGL2 example: https://github.com/ocornut/imgui/pull/801
- Unmerged PR: Native Win32 and OSX example: https://github.com/ocornut/imgui/pull/281
- Unmerged PR: Android Example: https://github.com/ocornut/imgui/pull/421
- Cinder: https://github.com/simongeilfus/Cinder-ImGui
- cocos2d-x: https://github.com/c0i/imguix and https://github.com/ocornut/imgui/issues/551
- Flexium/SFML (FlexGUI): https://github.com/DXsmiley/FlexGUI
- GML/GameMaker Studio 2 (ImGuiGML): https://marketplace.yoyogames.com/assets/6221/imguigml
- Irrlicht Engine (IrrIMGUI): https://github.com/ZahlGraf/IrrIMGUI
- Ogre: https://bitbucket.org/LMCrashy/ogreimgui/src
- OpenSceneGraph/OSG: https://gist.github.com/fulezi/d2442ca7626bf270226014501357042c
- openFrameworks (ofxImGui): https://github.com/jvcleave/ofxImGui
- LÖVE+LUA: https://github.com/slages/love-imgui
- NanoRT (software raytraced): https://github.com/syoyo/imgui/tree/nanort/examples/raytrace_example
- Qt3d: https://github.com/alpqr/imgui-qt3d
- SFML: https://github.com/EliasD/imgui-sfml or https://github.com/Mischa-Alff/imgui-backends
- Sokol (sample): https://github.com/floooh/sokol-samples/blob/master/glfw/imgui-glfw.cc
- Unreal Engine 4: https://github.com/segross/UnrealImGui or https://github.com/sronsse/UnrealEngine_ImGui

### Misc

- Remote ImGui: send vertices over the network https://github.com/JordiRos/remoteimgui
- ImWindow: Window and GUI system, include docking/floating window, multi window and multi render support https://github.com/thennequin/ImWindow
- imgui_wm: based on ImWindow above https://github.com/bkaradzic/bgfx/tree/master/3rdparty/ocornut-imgui
- Docking solutions: https://github.com/ocornut/imgui/issues/351
- Fips (fips-imgui): fipsified imgui for fips build system https://github.com/fungos/fips-imgui

### Articles

OpenGLやDirectXなGUIにimguiが最強すぎる (Japanese)
<br>http://qiita.com/Ushio@github/items/446d78c881334919e156

Using ImGui with modern C++ and STL [...] Part 2. Some tips and tricks.
<br>https://eliasdaler.github.io/using-imgui-with-sfml-pt2