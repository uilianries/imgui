## Language Bindings

_NB: those bindings may be more or less maintained, more or less close to the spirit of original API. People who create language bindings sometimes haven't used the C++ API themselves. ImGui was designed for C++ and some of the subtleties may be lost in translation with other languages. If your language supports it, I would suggest replicating the function overloading and default parameters used in the original, else the API may be harder to use. In doubt, always check the original C++ version first!_

| Language | Project |
|------------|---|
| Beef       | **imgui-beef**: Beef wrapper library for Dear ImGui<br>https://github.com/qzole/imgui-beef
| C          | **cimgui**: auto-generated c-api wrapper for Dear ImGui <br>\*\***(json/lua output can be used to automatically generate other bindings**)\*\*<br>https://github.com/cimgui/cimgui |
| C#/.Net    | **ImGui.NET**: An ImGui wrapper for .NET Core <br>https://github.com/mellinoe/ImGui.NET |
| ChaiScript | **imgui-chaiscript**: ChaiScript bindings for ImGui <br>https://github.com/JuJuBoSc/imgui-chaiscript |
| CovScript  | **covscript-imgui**: ImGui Extension for CovScript (Covariant) <br>https://github.com/covscript/covscript-imgui |
| D          | **DerelictImgui**: Dynamic bindings to cimgui for the D programming language <br>https://github.com/Extrawurst/DerelictImgui |
| Go         | **imgui-go**: Go wrapper library for "Dear ImGui" <br> https://github.com/inkyblackness/imgui-go |
| Haskell    | **imgui-haskell**: Haskell bindings for Dear ImGui <br>https://github.com/dbousamra/imgui-haskell
| Haxe/hxcpp | **linc_imgui**: binding for imgui <br>https://github.com/Aidan63/linc_imgui |
| Haxe/Heaps | **hlimgui**: [Heaps](https://heaps.io/) game engine binding for Dear ImGui <br>https://github.com/haddock7/hlimgui |
| Java       | **jimgui**: Pure Java binding for dear imgui <br>https://github.com/ice1000/jimgui <br>**imgui-java**: A handcrafted/generated Java binding for Dear ImGui<br>https://github.com/SpaiR/imgui-java |
| JavaScript | **imgui-js**: JavaScript bindings for Dear ImGui using Emscripten and TypeScript <br>https://github.com/flyover/imgui-js + also see [web demo](https://flyover.github.io/imgui-js/example/) |
| Julia      | **CImGui.jl**: Julia wrapper for cimgui <br>https://github.com/Gnimuc/CImGui.jL |
| Kotlin     | **kotlin-imgui**: Kotlin bindings for Dear ImGui<br>https://github.com/Dominaezzz/kotlin-imgui
| Lua        | **LuaJIT-ImGui**: LuaJIT ffi binding for imgui and implementations <br>https://github.com/sonoro1234/LuaJIT-ImGui <br>**imgui_lua_bindings**: imgui bindings for lua (also see LÖVE binding) <br>https://github.com/patrickriordan/imgui_lua_bindings <br> **lua-ffi-bindings**: FFI bindings for LuaJIT <br>https://github.com/thenumbernine/lua-ffi-bindings <br>**sol2_imgui_bindings**: ImGui bindings for Sol2 <br>https://github.com/MSeys/sol2_ImGui_Bindings |
| Nim        | **nim-imgui**: cimgui bindings for Nim <br>https://github.com/nimgl/imgui |
| Odin       | **odin-imgui**: Odin binding for Dear ImGui <br>https://github.com/ThisDrunkDane/odin-imgui |
| Pascal     | **imgui-pas**: pascal bindings for imgui <br>https://github.com/dpethes/imgui-pas |
| PureBasic | **pb-cimgui**: PureBasic interface to CImGui Wrapper <br>https://github.com/hippyau/pb-cimgui  |
| Python     | **pyimgui**: Cython-based Python bindings for dear imgui <br>https://github.com/swistakm/pyimgui <br> **DearPyGui**: A Python GUI framework built from Dear Imgui <br>https://github.com/hoffstadt/DearPyGui <br>**Bimpy**: Bundled imgui for python <br>https://github.com/podgorskiy/bimpy <br> **CyImGui**: Python bindings for ImGui using Cython. (obsolete) <br>https://github.com/chromy/cyimgui <br> **Ogre-imgui**: <br> https://github.com/OGRECave/ogre-imgui <br>**deargui**: Python bindings for dear imgui, generated with clang and pybind11 <br>https://github.com/cammm/deargui |
| Ruby | **ruby-imgui**: Yet another ImGui wrapper for Ruby <br>https://github.com/vaiorabbit/ruby-imgui |
| Rust | **imgui-rs**: Rust bindings for ImGui <br>https://github.com/Gekkio/imgui-rs <br>**imgui-rust**: Alternative (personal) imgui rust bindings <br>https://github.com/nsf/imgui-rust <br> **ImStr** Patch by @bitshifter to use string-range more commonly instead of zero-terminated strings. <br>https://github.com/ocornut/imgui/pull/683 <br>**rust-imgui-opengl-renderer** <br>https://github.com/michaelfairley/rust-imgui-opengl-renderer|
| Swift  | **SwiftGui**: an experimental API inspired by SwiftUI declarative code, using Dear ImGui and running on OSX and iOS.<br>https://github.com/erickjung/SwiftGUI<br>**SwiftImGui**: Swift wrapper around Dear imgui for macOS, iOS and linux<br>https://github.com/ctreffs/SwiftImGui<br>**Swift-imgui**: Dear ImGui Swift Wrapper API for macOS and iOS <br>https://github.com/mnmly/Swift-imgui |

## Framework/Engine Bindings/Backends

Main repository include examples for DirectX9, DirectX10, DirectX11, DirectX12, Metal, OpenGL2/3, Vulkan, iOS, Allegro 5, and Marmalade, using frameworks such as Glfw, SDL2, Win32, Cocoa. 
<br>https://github.com/ocornut/imgui/tree/master/examples

| Framework | Project |
|------------|---|
| Android | Unmerged PR: [#421](https://github.com/ocornut/imgui/pull/421) (old example design, should not be needed) |
| AGS / Adventure Game Studio | **agsimgui**:<br>https://github.com/ericoporto/agsimgui
| Amethyst | **amethyst-imgui**:<br>https://github.com/amethyst/amethyst-imgui
| bsf | **bsfimgui**:<br>https://github.com/pgruenbacher/bsfImgui | 
| Cinder | **Cinder-ImGui**:<br>https://github.com/simongeilfus/Cinder-ImGui
| Cocos2d-x | **imguix**:<br>https://github.com/c0i/imguix <br>**cocos2dx-imgui**:<br>https://github.com/Mjarkiew/cocos2dx-imgui and [#551](https://github.com/ocornut/imgui/issues/551)
| Diligent Engine | **DiligentTools**:<br>[DiligentTools](https://github.com/DiligentGraphics/DiligentTools/blob/master/Imgui/src/ImGuiImplDiligent.cpp), [example](https://github.com/DiligentGraphics/DiligentSamples/tree/master/Samples/ImguiDemo) |
| Ebiten | **ebiten-imgui**:<br>https://github.com/gabstv/ebiten-imgui |
| Flexium | **FlexGUI**:<br>https://github.com/DXsmiley/FlexGUI |
| GML / GameMaker Studio 2 | **ImGuiGML**:<br>https://marketplace.yoyogames.com/assets/6221/imguigml |
| Godot | **imgui-godot**:<br>https://github.com/pkdawson/imgui-godot
| GLEQ | Event processing:<br>[#3034](https://github.com/ocornut/imgui/issues/3034)
| GTK3 + OpenGL3 | **imgui_impl_gtk3**:<br>Unmerged PR: [#2032](https://github.com/ocornut/imgui/pull/2032) |
| Irrlicht Engine | **IrrIMGUI**:<br>https://github.com/ZahlGraf/IrrIMGUI |
| LÖVE+LUA | **love-imgui**:<br>https://github.com/slages/love-imgui<br>**love-imgui (fork)**:<br>https://github.com/MikuAuahDark/love-imgui |
| Magnum | **magnum-integration**:<br>https://github.com/mosra/magnum-integration, [doc](https://doc.magnum.graphics/magnum/namespaceMagnum_1_1ImGuiIntegration.html), [example](https://doc.magnum.graphics/magnum/examples-imgui.html) |
| NanoRT | **imgui_impl_raytrace**: <br>https://github.com/syoyo/imgui/tree/nanort/examples/raytrace_example |
| Nim Game Lib | **NimGL**:<br>https://github.com/nimgl/nimgl |
| Ogre | **ogre-imgui**:<br>https://github.com/OGRECave/ogre-imgui |
| openFrameworks | **ofxImGui**:<br>https://github.com/jvcleave/ofxImGui
| OpenSceneGraph/OSG | **imgui-osg**:<br>https://github.com/Tordan/imgui-osg and older gist: https://gist.github.com/fulezi/d2442ca7626bf270226014501357042c |
| Orx | **ImGuiOrx**:<br>https://github.com/thegwydd/ImGuiOrx (was [#1843](https://github.com/ocornut/imgui/pull/1843)) |
| Photoshop | **Recipe: Custom UI for plug-ins using Dear ImGui**:<br>https://sonictk.github.io/ps_cpp_recipes/#recipe:customuiforplug-insusingimgui<br>https://github.com/sonictk/ps_cpp_recipes
| px_render | **px_render_imgui.h**:<br>https://github.com/pplux/px/blob/master/px_render_imgui.h (was [#1935](https://github.com/ocornut/imgui/pull/1935)) |
| Qt | **imgui-qt3d**:<br>https://github.com/alpqr/imgui-qt3d <br>**QOpenGLWindow (qtimgui)**:<br>https://github.com/seanchas116/qtimgui<br> **QtDirect3D**:<br>https://github.com/giladreich/QtDirect3D, qt6: https://github.com/alpqr/qvk6/tree/imgui/examples/rhi/imguidemo |
| SDL_Renderer | **imgui_sdl**:<br>https://github.com/Tyyppi77/imgui_sdl<br>_IMPORTANT: This is a software rendering back-end for SDL_Renderer. SDL_Renderer is an old component of SDL aimed at replacing graphics API, in my opinion it is a useless dead-end and no one should use SDL_Renderer. Even just using ImGui's ImDrawList + native OGL/DX back-ends will get you closer to something useful. Consider using SFML or openFrameworks or custom renderer instead of SDL + SDL_Renderer. (Clarification: SDL itself is good, we're talkig about SDL_Renderer here!)_
| SFML | **imgui-sfml**:<br>https://github.com/eliasdaler/imgui-sfml |
| Sokol | **sokol-samples**:<br>https://github.com/floooh/sokol-samples/blob/master/glfw/imgui-glfw.cc |
| Unity | **dear-imgui-unity**:<br>https://github.com/realgamessoftware/dear-imgui-unity
| Unreal Engine 4 | **UnrealImGui**:<br>https://github.com/segross/UnrealImGui <br>**UnrealEngine_ImGui**:<br>https://github.com/sronsse/UnrealEngine_ImGui
| vtk | **imgui-vtk**:<br>https://github.com/trlsmax/imgui-vtk
| Win32 (native) example | **example_win32_opengl3**:<br>Unmerged PR: [#2772](https://github.com/ocornut/imgui/pull/2772), [#281](https://github.com/ocornut/imgui/pull/281) (old example design) |
| Win32 GDI renderer | **imgui_impl_gdi**:<br>Unmerged PR: [#2724](https://github.com/ocornut/imgui/pull/2724)
| WxWidgets | **wxImGuiCanvas.h**:<br>https://github.com/ocornut/imgui/issues/1029


## Miscellaneous

| Purpose | Project |
|------------|---|
| Software renderer | **imgui_software_renderer** <br>https://github.com/emilk/imgui_software_renderer |
| Software renderer | **ImFastRast** <br>https://github.com/malamanteau/ImFastRast |
| Software renderer | **ImSoft** <br>https://github.com/LAK132/ImSoft |

## Port/rewrites

| Language | Project |
|------------|---|
| Kotlin     | **dear jvm imgui**: full JVM port/rewrite <br>https://github.com/kotlin-graphics/imgui |

