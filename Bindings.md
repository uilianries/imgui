## Language Bindings

_NB: those bindings may be more or less maintained, more or less close to the spirit of original API. People who create language bindings sometimes haven't used the C++ API themselves. ImGui was designed for C++ and some of the subtleties may be lost in translation with other languages. If your language supports it, I would suggest replicating the function overloading and default parameters used in the original, else the API may be harder to use. In doubt, always check the original C++ version first!_

| Language | Project |
|------------|---|
| C          | **cimgui**: auto-generated c-api wrapper for Dear ImGui <br>\*\***Output json/lua data which can be used to automatically generate other bindings**\*\*<br>https://github.com/cimgui/cimgui |
| C#/.Net    | **ImGui.NET**: An ImGui wrapper for .NET Core <br>https://github.com/mellinoe/ImGui.NET |
| ChaiScript | **imgui-chaiscript**: ChaiScript bindings for ImGui <br>https://github.com/JuJuBoSc/imgui-chaiscript |
| CovScript  | **covscript-imgui**: ImGui Extension for CovScript (Covariant) <br>https://github.com/covscript/covscript-imgui |
| D          | **DerelictImgui**: Dynamic bindings to cimgui for the D programming language <br>https://github.com/Extrawurst/DerelictImgui |
| Go         | **imgui-go**: Go wrapper library for "Dear ImGui" <br> https://github.com/inkyblackness/imgui-go <br>**go-imgui**: Go bindings for the dear imgui immediate mode GUI library <br>https://github.com/Armored-Dragon/go-imgui |
| Haskell    | **imgui-haskell**: Haskell bindings for Dear ImGui <br>https://github.com/dbousamra/imgui-haskell
| Haxe/hxcpp | **linc_imgui**: binding for imgui <br>https://github.com/Aidan63/linc_imgui |
| Java       | **jimgui**: Pure Java binding for dear imgui <br>https://github.com/ice1000/jimgui |
| JavaScript | **imgui-js**: JavaScript bindings for Dear ImGui using Emscripten and TypeScript <br>https://github.com/flyover/imgui-js + also see [web demo](https://flyover.github.io/imgui-js/example/) |
| Julia      | **CImGui.jl**: Julia wrapper for cimgui <br>https://github.com/Gnimuc/CImGui.jL |
| Lua        | **LuaJIT-ImGui**: LuaJIT ffi binding for imgui and implementations <br>https://github.com/sonoro1234/LuaJIT-ImGui <br>**imgui_lua_bindings**: imgui bindings for lua (also see LÖVE binding) <br>https://github.com/patrickriordan/imgui_lua_bindings <br> **lua-ffi-bindings**: FFI bindings for LuaJIT <br>https://github.com/thenumbernine/lua-ffi-bindings |
| Nim        | **nim-imgui**: cimgui bindings for Nim <br>https://github.com/nimgl/imgui |
| Odin       | **odin_dear_imgui**: Odin binding for Dear ImGui <br>https://github.com/ThisDrunkDane/odin-dear_imgui |
| Pascal     | **imgui-pas**: pascal bindings for imgui <br>https://github.com/dpethes/imgui-pas |
| PureBasic | **pb-cimgui**: PureBasic interface to CImGui Wrapper <br>https://github.com/hippyau/pb-cimgui  |
| Python     | **pyimgui**: Cython-based Python bindings for dear imgui <br>https://github.com/swistakm/pyimgui <br> **Bimpy**: Bundled imgui for python <br>https://github.com/podgorskiy/bimpy <br> **CyImGui**: Python bindings for ImGui using Cython. (obsolete) <br>https://github.com/chromy/cyimgui <br> **Ogre-imgui**: <br> https://github.com/OGRECave/ogre-imgui <br>**deargui**: Python bindings for dear imgui, generated with clang and pybind11 <br>https://github.com/cammm/deargui |
| Ruby | **ruby-imgui**: Yet another ImGui wrapper for Ruby <br>https://github.com/vaiorabbit/ruby-imgui |
| Rust | **imgui-rs**: Rust bindings for ImGui <br>https://github.com/Gekkio/imgui-rs <br>**imgui-rust**: Alternative (personal) imgui rust bindings <br>https://github.com/nsf/imgui-rust <br> **ImStr** Patch by @bitshifter to use string-range more commonly instead of zero-terminated strings. <br>https://github.com/ocornut/imgui/pull/683 <br>**rust-imgui-opengl-renderer** <br>https://github.com/michaelfairley/rust-imgui-opengl-renderer|
| Swift  | **SwiftGui**: an experimental API inspired by SwiftUI declarative code, using Dear ImGui and running on OSX and iOS.<br>https://github.com/erickjung/SwiftGUI<br>**SwiftImGui**: Swift wrapper around Dear imgui for macOS, iOS and linux<br>https://github.com/ctreffs/SwiftImGui<br>**Swift-imgui**: Dear ImGui Swift Wrapper API for macOS and iOS <br>https://github.com/mnmly/Swift-imgui |

## Framework/Engine Bindings

Main repository include examples for DirectX9, DirectX10, DirectX11, DirectX12, Metal, OpenGL2/3, Vulkan, iOS, Allegro 5, and Marmalade, using frameworks such as Glfw, SDL2, Win32, Cocoa. 
<br>https://github.com/ocornut/imgui/tree/master/examples

| Framework | Project |
|------------|---|
| Android | Unmerged PR: [#421](https://github.com/ocornut/imgui/pull/421) (old example design, should not be needed) |
| Amethyst | **amethyst-imgui**: https://github.com/amethyst/amethyst-imgui
| bsf | **bsfimgui**: https://github.com/pgruenbacher/bsfImgui | 
| Cinder | **Cinder-ImGui**: https://github.com/simongeilfus/Cinder-ImGui
| Cocos2d-x | **imguix**: https://github.com/c0i/imguix <br>**cocos2dx-imgui**: https://github.com/Mjarkiew/cocos2dx-imgui <br> and [#551](https://github.com/ocornut/imgui/issues/551)
| Diligent Engine | [DiligentTools](https://github.com/DiligentGraphics/DiligentTools/blob/master/Imgui/src/ImGuiImplDiligent.cpp), [example](https://github.com/DiligentGraphics/DiligentSamples/tree/master/Samples/ImguiDemo) |
| Flexium | **FlexGUI**: https://github.com/DXsmiley/FlexGUI |
| GML / GameMaker Studio 2 | **ImGuiGML**: https://marketplace.yoyogames.com/assets/6221/imguigml |
| GTK3 + OpenGL3 | Unmerged PR: [#2032](https://github.com/ocornut/imgui/pull/2032) |
| Irrlicht Engine | **IrrIMGUI**: https://github.com/ZahlGraf/IrrIMGUI |
| Ogre | **ogre-imgui**: https://github.com/OGRECave/ogre-imgui |
| OpenSceneGraph/OSG | **imgui-osg**: https://github.com/Tordan/imgui-osg<br>older gist: https://gist.github.com/fulezi/d2442ca7626bf270226014501357042c |
| openFrameworks | **ofxImGui**: https://github.com/jvcleave/ofxImGui
| Orx | **ImGuiOrx**: https://github.com/thegwydd/ImGuiOrx (was [#1843](https://github.com/ocornut/imgui/pull/1843)) |
| LÖVE+LUA | **love-imgui**: https://github.com/slages/love-imgui |
| Magnum | **magnum-integration**: https://github.com/mosra/magnum-integration, [doc](https://doc.magnum.graphics/magnum/namespaceMagnum_1_1ImGuiIntegration.html), [example](https://doc.magnum.graphics/magnum/examples-imgui.html) |
| NanoRT | https://github.com/syoyo/imgui/tree/nanort/examples/raytrace_example |
| Nim Game Lib | https://github.com/nimgl/nimgl |
| px_render | **px_render_imgui.h**: https://github.com/pplux/px/blob/master/px_render_imgui.h (was [#1935](https://github.com/ocornut/imgui/pull/1935)) |
| Qt | **imgui-qt3d**: https://github.com/alpqr/imgui-qt3d <br>**QOpenGLWindow (qtimgui)**: [#1910](https://github.com/ocornut/imgui/issues/1910), **QtDirect3D**: https://github.com/giladreich/QtDirect3D, qt6: https://github.com/alpqr/qvk6/tree/imgui/examples/rhi/imguidemo |
| SFML | **imgui-sfml**: https://github.com/eliasdaler/imgui-sfml |
| Sokol | https://github.com/floooh/sokol-samples/blob/master/glfw/imgui-glfw.cc |
| Unreal Engine 4 | **UnrealImGui**: https://github.com/segross/UnrealImGui <br>**UnrealEngine_ImGui**: https://github.com/sronsse/UnrealEngine_ImGui
| vtk | **imgui-vtk**: https://github.com/trlsmax/imgui-vtk
| Win32 (native) example | Unmerged PR: [#2772](https://github.com/ocornut/imgui/pull/2772), [#281](https://github.com/ocornut/imgui/pull/281) (old example design) |

## Miscellaneous

| Purpose | Project |
|------------|---|
| Software renderer | **imgui_software_renderer**: https://github.com/emilk/imgui_software_renderer |
| Software renderer | **ImFastRast**: https://github.com/malamanteau/ImFastRast |
| Software renderer | **ImSoft**: https://github.com/LAK132/ImSoft |

## Port/rewrites

| Language | Project |
|------------|---|
| Kotlin     | **dear jvm imgui**: full JVM port/rewrite <br>https://github.com/kotlin-graphics/imgui |

