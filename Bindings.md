## Index

- [Binding Generators](#binding-generators)
- [Language Bindings](#language-bindings)
- [Framework/Engine Backends](#frameworkengine-backends)
- [Miscellaneous](#Miscellaneous)
- [Ports, Rewrites, Clones](#ports-rewrites-clones)

## Binding Generators

### cimgui

https://github.com/cimgui/cimgui
<BR>Output C API + output metadata (see `generator/output/` folder) which can be used to automatically generate other bindings.

### dear_bindings

https://github.com/dearimgui/dear_bindings
<BR>Dear Bindings is tool to generate a C API for Dear ImGui, and metadata so other languages can easily generate their own bindings on top.

----

## Language Bindings

Note: those bindings may be more or less maintained, more or less close to the spirit of original API. People who create language bindings sometimes haven't used the C++ API themselves. Dear ImGui was designed for C++ and some of the subtleties may be lost in translation with other languages. If your language supports it, I would suggest replicating the function overloading and default parameters used in the original, else the API may be harder to use. In doubt, always check the original C++ version first!

Now on to the list...

| Language | Project |
|------------|---|
| Beef       | **imgui-beef**: auto-generated Beef wrapper library for Dear ImGui<br>https://github.com/RogueMacro/imgui-beef
| C          | **cimgui**: auto-generated c-api wrapper for Dear ImGui <br>\*\***(metadata output from cimgui can be used to automatically generate other bindings**)\*\*<br>https://github.com/cimgui/cimgui<br><br>**dear_bindings**: auto-generated c-api wrapper for Dear ImGui <br>\*\***(metadata output from cimgui can be used to automatically generate other bindings**)\*\*<br>https://github.com/dearimgui/dear_bindings |
| C#/.Net    | **ImGui.NET**: An ImGui wrapper for .NET Core <br>https://github.com/mellinoe/ImGui.NET <br> **DearImGui**: imgui + implot for .NET + a controller for OpenGL (OpenTK) <br> https://github.com/aybe/DearImGui|
| C++17      | **ImGuiWrapper**: CMakeList wrapper and C++17 RAII encapsulation for accessing Imgui |
| ChaiScript | **imgui-chaiscript**: ChaiScript bindings for ImGui <br>https://github.com/JuJuBoSc/imgui-chaiscript |
| CovScript  | **covscript-imgui**: ImGui Extension for CovScript (Covariant) <br>https://github.com/covscript/covscript-imgui |
| Crystal    | **crystal-imgui**: Crystal bindings to Dear ImGui<br>https://github.com/oprypin/crystal-imgui
| D          | **bindbc-imgui**: Dynamic and static bindings to imgui, compatible with -betterC, @nogc, and nothrow<br>https://github.com/Inochi2D/bindbc-imgui<br>**DerelictImgui**: Dynamic bindings to cimgui for the D programming language <br>https://github.com/Extrawurst/DerelictImgui |
| Go         | **cimgui-go**: Go wrapper library for "Dear ImGui" <br> https://github.com/AllenDang/cimgui-go |
| Haskell    | **dear-imgui.hs**: Haskell bindings to Dear ImGui,<br>https://github.com/haskell-game/dear-imgui.hs<br>**imgui-haskell**: Haskell bindings for Dear ImGui <br>https://github.com/dbousamra/imgui-haskell
| Haxe/hxcpp | **linc_imgui**: binding for imgui <br>https://github.com/Aidan63/linc_imgui |
| Haxe/Heaps | **hlimgui**: [Heaps](https://heaps.io/) game engine binding for Dear ImGui <br>https://github.com/haddock7/hlimgui |
| Java       | **jimgui**: Pure Java binding for dear imgui <br>https://github.com/ice1000/jimgui <br>**imgui-java**: JNI based binding for Dear ImGui<br>https://github.com/SpaiR/imgui-java |
| JavaScript | **imgui-js**: JavaScript bindings for Dear ImGui using Emscripten and TypeScript <br>https://github.com/flyover/imgui-js + also see [web demo](https://flyover.github.io/imgui-js/example/) |
| Julia      | **CImGui.jl**: Julia wrapper for cimgui <br>https://github.com/Gnimuc/CImGui.jL |
| Kotlin     | **kotlin-imgui**: Kotlin bindings for Dear ImGui<br>https://github.com/Dominaezzz/kotlin-imgui
| Lobster    | **imgui.lobster**: <br>http://strlen.com/lobster/
| Lua        | **LuaJIT-ImGui**: LuaJIT ffi binding for imgui and implementations <br>https://github.com/sonoro1234/LuaJIT-ImGui <br>**imgui_lua_bindings**: imgui bindings for lua (also see LÖVE binding) <br>https://github.com/patrickriordan/imgui_lua_bindings (unmaintained) <br>https://github.com/megumumpkin/imgui_lua_bindings (up to date fork) <br> **lua-ffi-bindings**: FFI bindings for LuaJIT <br>https://github.com/thenumbernine/lua-ffi-bindings <br>**sol2_imgui_bindings**: ImGui bindings for Sol2 <br>https://github.com/MSeys/sol2_ImGui_Bindings <br>**Gideros_ImGui**: ImGui bindings for Gideros Studio <br>https://github.com/MultiPain/Gideros_ImGui|
| Nim        | **nim-imgui**: cimgui bindings for Nim <br>https://github.com/nimgl/imgui |
| Odin       | **odin-imgui**: Odin binding for Dear ImGui <br>https://github.com/ThisDrunkDane/odin-imgui |
| Pascal     | **imgui-pas**: pascal bindings for imgui <br>https://github.com/dpethes/imgui-pas |
| PureBasic | **pb-cimgui**: PureBasic interface to CImGui Wrapper <br>https://github.com/hippyau/pb-cimgui  |
| Python     | **pyimgui**: Cython-based Python bindings for dear imgui <br>https://github.com/swistakm/pyimgui <br> **DearPyGui**: A Python GUI framework built from Dear Imgui <br>https://github.com/hoffstadt/DearPyGui <br>**Bimpy**: Bundled imgui for python <br>https://github.com/podgorskiy/bimpy <br> **CyImGui**: Python bindings for ImGui using Cython. (obsolete) <br>https://github.com/chromy/cyimgui <br> **Ogre-imgui**: <br> https://github.com/OGRECave/ogre-imgui <br>**deargui**: Python bindings for dear imgui, generated with clang and pybind11 <br>https://github.com/cammm/deargui <br>**Dear ImGui Bundle**: autogenerated bindings and stubs for ImGui (as well as ImPlot, ImGuizmo, node-editor, etc.)<br>https://github.com/pthom/imgui_bundle |
| ReaScript | **ReaImGui**: ReaScript binding for Dear ImGui<br>https://forum.cockos.com/showthread.php?t=250419
| Ruby | **ruby-imgui**: Yet another ImGui wrapper for Ruby <br>https://github.com/vaiorabbit/ruby-imgui |
| Rust | **imgui-rs**: Rust bindings for ImGui <br>https://github.com/imgui-rs/imgui-rs <br>**imgui-rust**: Alternative (personal) imgui rust bindings <br>https://github.com/nsf/imgui-rust <br> **ImStrv** Patch by @bitshifter/@rokups to use string-range more commonly instead of zero-terminated strings. <br>https://github.com/ocornut/imgui/pull/3038 <br>**rust-imgui-opengl-renderer** <br>https://github.com/michaelfairley/rust-imgui-opengl-renderer|
| Swift  | **SwiftGui**: an experimental API inspired by SwiftUI declarative code, using Dear ImGui and running on OSX and iOS.<br>https://github.com/erickjung/SwiftGUI<br>**SwiftImGui**: Swift wrapper around Dear imgui for macOS, iOS and linux<br>https://github.com/ctreffs/SwiftImGui<br>**Swift-imgui**: Dear ImGui Swift Wrapper API for macOS and iOS <br>https://github.com/mnmly/Swift-imgui |
| Zig | Zig bindings for ocornut/imgui, generated using cimgui/cimgui https://github.com/SpexGuy/Zig-ImGui

## Framework/Engine Backends

Main repository include examples for DirectX9, DirectX10, DirectX11, DirectX12, Metal, OpenGL2/3, Vulkan, SDL_Renderer, iOS, WebGPU, using frameworks such as GLFW, SDL2, Win32, GLUT, Android, OSX/Cocoa, Allegro. See [examples/](https://github.com/ocornut/imgui/tree/master/examples) and [BACKENDS.md](https://github.com/ocornut/imgui/blob/master/docs/BACKENDS.md) for details.

Other backends:

| Framework | Project |
|------------|---|
| AGS / Adventure Game Studio | **agsimgui**:<br>https://github.com/ericoporto/agsimgui
| Amethyst | **amethyst-imgui**:<br>https://github.com/amethyst/amethyst-imgui
| Blender | **BlenderImgui**:<br>https://github.com/eliemichel/BlenderImgui
| bsf | **bsfimgui**:<br>https://github.com/pgruenbacher/bsfImgui | 
| Cinder | **Cinder-ImGui**:<br>https://github.com/cinder/Cinder/blob/master/include/cinder/CinderImGui.h
| Cocos2d-x | **imguix**:<br>https://github.com/c0i/imguix <br>**cocos2dx-imgui**:<br>https://github.com/Mjarkiew/cocos2dx-imgui, https://github.com/Xrysnow/cocos2d-x-imgui and [#551](https://github.com/ocornut/imgui/issues/551)<br>**ImGui for axmol**:<br>https://github.com/axmolengine/axmol/tree/dev/extensions/ImGui
| Defold | **extension-imgui**:<br>https://github.com/britzl/extension-imgui
| Diligent Engine | **DiligentTools**:<br>[DiligentTools](https://github.com/DiligentGraphics/DiligentTools/blob/master/Imgui/src/ImGuiImplDiligent.cpp), [example](https://github.com/DiligentGraphics/DiligentSamples/tree/master/Samples/ImguiDemo) |
| Ebiten | **ebiten-imgui**:<br>https://github.com/gabstv/ebiten-imgui |
| Flexium | **FlexGUI**:<br>https://github.com/DXsmiley/FlexGUI |
| GML / GameMaker Studio 2 | **ImGuiGML**:<br>https://marketplace.yoyogames.com/assets/6221/imguigml<br>**ImGui_GM**:<br>https://github.com/nommiin/ImGui_GM<br> |
| Godot | **imgui-godot**:<br>https://github.com/pkdawson/imgui-godot<br>**godot-dear-imgui**:<br>https://github.com/Blackdrop-Interactive-AB/godot-dear-imgui
| GLEQ | Event processing:<br>[#3034](https://github.com/ocornut/imgui/issues/3034)
| GTK3 + OpenGL3 | **imgui_impl_gtk3**:<br>Unmerged PR: [#2032](https://github.com/ocornut/imgui/pull/2032) |
| Irrlicht Engine | **IrrIMGUI**:<br>https://github.com/Armmegon/Irrlicht-ImGui |
| JUCE | **imgui_juce**:<br>https://github.com/Krasjet/imgui_juce |
| LÖVE+LUA | **love-imgui**:<br>https://github.com/slages/love-imgui<br>**love-imgui (fork)**:<br>https://github.com/MikuAuahDark/love-imgui<br>**LuaJIT-ImGui (ffi)**:<br>https://github.com/sonoro1234/LuaJIT-ImGui<br>**cimgui-love (ffi)**:<br>https://github.com/apicici/cimgui-love |
| Mach engine | **mach/imgui**:<br>https://github.com/machlibs/imgui
| Magnum | **magnum-integration**:<br>https://github.com/mosra/magnum-integration, [doc](https://doc.magnum.graphics/magnum/namespaceMagnum_1_1ImGuiIntegration.html), [example](https://doc.magnum.graphics/magnum/examples-imgui.html) |
| Marmalade | **imgui_impl_marmalade**: <br>[backend](https://github.com/ocornut/imgui/tree/v1.85/backends) + [example](https://github.com/ocornut/imgui/tree/v1.85/examples/example_marmalade)
| Monogame | **ImGui.NET for MonoGame**: <br>https://github.com/roy-t/ImGui.NET
| NanoRT | **imgui_impl_raytrace**: <br>https://github.com/syoyo/imgui/tree/nanort/examples/raytrace_example |
| nCine | **nCine Out-of-the-box integration**: <br>https://github.com/nCine/nCine and [example 1](https://github.com/nCine/nCine/blob/master/tests/apptest_scene.cpp), [example 2](https://github.com/nCine/nCine/blob/master/tests/apptest_simdbench.cpp)
| Nim Game Lib | **NimGL**:<br>https://github.com/nimgl/nimgl |
| Nintendo 3DS (homebrew) | **libctru/libcitro3d**:<br>https://github.com/mtheall/ftpd/tree/master/source/3ds |
| Nintendo Switch (homebrew) | **libnx/libdeko3d**:<br>https://github.com/mtheall/ftpd/tree/master/source/switch<br>https://github.com/scturtle/imgui_deko3d_example |
| Nintendo Wii U (homebrew) | **wut/GX2**:<br>https://github.com/GaryOderNichts/imgui |
| Ogre | **ogre-imgui**:<br>https://github.com/OGRECave/ogre-imgui |
| openFrameworks | **ofxImGui**:<br>https://github.com/jvcleave/ofxImGui
| OpenSceneGraph/OSG | **imgui-osg**:<br>https://github.com/Tordan/imgui-osg and older gist: https://gist.github.com/fulezi/d2442ca7626bf270226014501357042c |
| Orx | **ImGuiOrx**:<br>https://github.com/thegwydd/ImGuiOrx (was [#1843](https://github.com/ocornut/imgui/pull/1843)) |
| Photoshop | **Recipe: Custom UI for plug-ins using Dear ImGui**:<br>https://sonictk.github.io/ps_cpp_recipes/#recipe:customuiforplug-insusingimgui<br>https://github.com/sonictk/ps_cpp_recipes
| px_render | **px_render_imgui.h**:<br>https://github.com/pplux/px/blob/master/px_render_imgui.h (was [#1935](https://github.com/ocornut/imgui/pull/1935)) |
| raylib | **rlImGui**:<br>https://github.com/raylib-extras/rlImGui</br> |
| Qt | **imgui-qt3d**:<br>https://github.com/alpqr/imgui-qt3d<br><br>**QQuickItem (qrhiimgui2)**:<br>Qt >= 6.4 https://github.com/alpqr/qrhiimgui2<br>Has a sample to integrate it in a QWindow if not using QtQuick. Supports imgui 1.87+<br><br>**QQuickItem (qrhiimgui)**:<br>Qt >= 6 https://github.com/alpqr/qrhiimgui<br>Has a sample to integrate it in a QWindow if not using QtQuick.<br>_IMPORTANT: Requires a patch merged in a newer version of Qt 6 in order to use it in QML. Consider using qrhiimgui2 instead._<br><br>**QQuickItem (imgui-qtquick)**:<br>(OpenGL only, Qt 5+) https://github.com/alpqr/imgui-qtquick<br>**QOpenGLWindow (qtimgui)**:<br>https://github.com/seanchas116/qtimgui<br> **QtDirect3D**:<br>https://github.com/giladreich/QtDirect3D |
| SDL_Renderer | **imgui_sdl**:<br>https://github.com/Tyyppi77/imgui_sdl<br>_IMPORTANT: This is a software rendering back-end for SDL_Renderer. SDL_Renderer is NOT the same as SDL. SDL_Renderer is an optional component of SDL aimed at replacing graphics API, ihmo it is outdated, not well designed, and doesn't bring much value. Please note you can use traditional OpenGL/DX9/DX11 backends in SDL even if you use SDL_Renderer (you'll need to chose the backend based on runtime graphics API). About SDL_Renderer not bringing much value: if you need high-level graphics helpers, Consider using SFML or openFrameworks or custom renderer instead of SDL + SDL_Renderer._
| SFML | **imgui-sfml**:<br>https://github.com/SFML/imgui-sfml |
| Sokol | **sokol-samples**:<br>https://github.com/floooh/sokol-samples/blob/master/glfw/imgui-glfw.cc |
| Unity | **dear-imgui-unity**:<br>https://github.com/realgamessoftware/dear-imgui-unity<br>**uimgui**:<br>https://github.com/psydack/uimgui
| Unreal Engine 4/5 | **UnrealImGui**:<br>https://github.com/segross/UnrealImGui <br>fork: https://github.com/benui-dev/UnrealImGui <br>**UnrealEngine_ImGui**:<br>https://github.com/sronsse/UnrealEngine_ImGui<br>**UnrealNetImgui** (plugin for NetImgui):<br>https://github.com/sammyfreg/UnrealNetImgui<BR><BR>Also see: **UnrealImGuiTools** "A set of tools and utilities for use with Unreal Engine projects using ImGui."<BR>https://github.com/nakdeyes/UnrealImGuiTools
| vtk | **imgui-vtk**:<br>https://github.com/trlsmax/imgui-vtk
| VulkanHpp | **ImGui-VulkanHpp**:<br>https://github.com/takiyu/ImGui-VulkanHpp
| VulkanSceneGraph | **vsgImGui**:<br>https://github.com/vsg-dev/vsgImGui
| Win32 (native) example | **example_win32_opengl3**:<br>Unmerged PR: [#2772](https://github.com/ocornut/imgui/pull/2772), [#281](https://github.com/ocornut/imgui/pull/281) (old example design) |
| Win32 GDI renderer | **imgui_impl_gdi**:<br>Unmerged PR: [#2724](https://github.com/ocornut/imgui/pull/2724)
| WxWidgets | **wxImGuiCanvas.h**:<br>https://github.com/ocornut/imgui/issues/1029

## Miscellaneous

| Purpose | Project |
|------------|---|
| Software renderer | **imgui_software_renderer** <br>https://github.com/emilk/imgui_software_renderer |
| Software renderer | **ImFastRast** <br>https://github.com/malamanteau/ImFastRast |
| Software renderer | **ImSoft** <br>https://github.com/LAK132/ImSoft |
| ImGui on Arduino example | **ImDuino** <br>https://github.com/LAK132/ImDuino |

## Ports, Rewrites, Clones
(notable rewrites or clones, those are not supported on this repository)

| Language | Project |
|------------|---|
| Kotlin     | **dear jvm imgui**: full JVM port/rewrite <br>https://github.com/kotlin-graphics/imgui |
| Javascript | **imgui-njs**: imgui-njs is a manual-port / partial-rewrite of dear imgui <br>https://github.com/cannerycoders/imgui-njs |
