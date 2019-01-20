### Language bindings

_NB: those bindings may be more or less maintained, more or less close to the spirit of original API. People who create language bindings sometimes haven't used the C++ API themselves. ImGui was designed for C++ and some of the subtleties may be lost in translation with other languages. If your language supports it, I would suggest replicating the function overloading and default parameters used in the original, else the API may be harder to use. In doubt, always check the original C++ version first!_

**C (cimgui): auto-generated c-api wrapper for Dear ImGui**
**<br>also output json/lua data which can be used to automatically generate other bindings**
<br>https://github.com/cimgui/cimgui

C#/.Net (ImGui.NET): An ImGui wrapper for .NET Core
<br>https://github.com/mellinoe/ImGui.NET

ChaiScript (imgui-chaiscript): ChaiScript bindings for ImGui
<br>https://github.com/JuJuBoSc/imgui-chaiscript

CovScript (covscript-imgui): ImGui Extension for CovScript (Covariant)
<br>https://github.com/covscript/covscript-imgui

D (DerelictImgui): Dynamic bindings to the cimgui library for the D programming language
<br>https://github.com/Extrawurst/DerelictImgui

Go (imgui-go): Go wrapper library for "Dear ImGui"
<br>https://github.com/inkyblackness/imgui-go

Go (go-imgui): Go bindings for the dear imgui immediate mode GUI library 
<br>https://github.com/Armored-Dragon/go-imgui

Haxe/hxcpp (linc_imgui): binding for imgui
<br>https://github.com/Aidan63/linc_imgui

Java (jimgui): Pure Java binding for dear imgui 
<br>https://github.com/ice1000/jimgui

JavaScript (imgui-js): JavaScript bindings for Dear ImGui using Emscripten and TypeScript
<br>https://github.com/flyover/imgui-js + also see [web demo](https://flyover.github.io/imgui-js/example/)

Lua (LuaJIT-ImGui): LuaJIT ffi binding for imgui and implementations
<br>https://github.com/sonoro1234/LuaJIT-ImGui

Lua: imgui bindings for lua (also see: LOVE binding)
<br>https://github.com/patrickriordan/imgui_lua_bindings

Lua: FFI bindings for LuaJIT
<br>https://github.com/thenumbernine/lua-ffi-bindings

Nim: cimgui bindings for Nim
<br>https://github.com/zacharycarter/nimgui

Odin: Odin binding for Dear ImGui
<br>https://github.com/ThisDrunkDane/odin-dear_imgui

Pascal (imgui-pas): pascal bindings for imgui
<br>https://github.com/dpethes/imgui-pas

Python (CyImGui): Python bindings for ImGui using Cython.
<br>https://github.com/chromy/cyimgui

Python (pyimgui): Cython-based Python bindings for dear imgui
<br>https://github.com/swistakm/pyimgui

PureBasic (pb-cimgui): PureBasic interface to CImGui Wrapper
<br>https://github.com/hippyau/pb-cimgui

Ruby (ruby-imgui): Yet another ImGui wrapper for Ruby
<br>https://github.com/vaiorabbit/ruby-imgui

Rust (imgui-rs): Rust bindings for ImGui
<br>https://github.com/Gekkio/imgui-rs

Rust (imgui-rust): Alternative (personal) imgui rust bindings
<br>https://github.com/nsf/imgui-rust

Rust: "ImStr" Patch by @bitshifter to use string-range more commonly instead of zero-terminated strings.
<br>https://github.com/ocornut/imgui/pull/683

Rust: imgui-opengl-renderer
<br>https://github.com/michaelfairley/rust-imgui-opengl-renderer

Swift (Swift-imgui): Dear ImGui Swift Wrapper API for macOS and iOS 
<br>https://github.com/mnmly/Swift-imgui

### Port/rewrites

Java - JVM port/rewrite, written in Kotlin
<br>https://github.com/kotlin-graphics/imgui

### Framework/engine bindings

Main repository include examples for DirectX9, DirectX10, DirectX11, DirectX12, Metal, OpenGL2/3, Vulkan, iOS, Allegro 5, and Marmalade, using frameworks such as Glfw, SDL2, Win32, Cocoa. 
<br>https://github.com/ocornut/imgui/tree/master/examples

- Unmerged PR: SDL2 + OpenGLES + Emscripten example: https://github.com/ocornut/imgui/pull/336 (old example design)
- Unmerged PR: Native Win32 and OSX example: https://github.com/ocornut/imgui/pull/281 (old example design)
- Unmerged PR: Android Example: https://github.com/ocornut/imgui/pull/421 (old example design)
- Cinder: https://github.com/simongeilfus/Cinder-ImGui
- Cocos2d-x: https://github.com/c0i/imguix and https://github.com/ocornut/imgui/issues/551
- Flexium (FlexGUI): https://github.com/DXsmiley/FlexGUI
- GML/GameMaker Studio 2 (ImGuiGML): https://marketplace.yoyogames.com/assets/6221/imguigml
- Irrlicht Engine (IrrIMGUI): https://github.com/ZahlGraf/IrrIMGUI
- Ogre: https://bitbucket.org/LMCrashy/ogreimgui/src, https://github.com/OGRECave/ogre-imgui
- OpenSceneGraph/OSG: https://gist.github.com/fulezi/d2442ca7626bf270226014501357042c
- openFrameworks (ofxImGui): https://github.com/jvcleave/ofxImGui
- Orx: https://github.com/ocornut/imgui/pull/1843
- LÖVE+LUA: https://github.com/slages/love-imgui
- Magnum: https://github.com/mosra/magnum-integration ([doc](https://doc.magnum.graphics/magnum/namespaceMagnum_1_1ImGuiIntegration.html), [example](https://doc.magnum.graphics/magnum/examples-imgui.html))
- NanoRT (software raytraced): https://github.com/syoyo/imgui/tree/nanort/examples/raytrace_example
- Nim Game Lib: https://github.com/lmariscal/nimgl
- px_render: https://github.com/ocornut/imgui/pull/1935
- Qt: [imgui-qt3d](https://github.com/alpqr/imgui-qt3d) / [QOpenGLWindow (qtimgui)](https://github.com/ocornut/imgui/issues/1910) / [QtDirect3D](https://github.com/giladreich/QtDirect3D) / [qt6](https://github.com/alpqr/qvk6/tree/imgui/examples/rhi/imguidemo)
- SFML: https://github.com/EliasD/imgui-sfml (or older: https://github.com/Mischa-Alff/imgui-backends)
- Software renderer: https://github.com/emilk/imgui_software_renderer
- Sokol (sample): https://github.com/floooh/sokol-samples/blob/master/glfw/imgui-glfw.cc
- Unreal Engine 4: https://github.com/segross/UnrealImGui or https://github.com/sronsse/UnrealEngine_ImGui
- vtk (imgui-vtk): https://github.com/trlsmax/imgui-vtk