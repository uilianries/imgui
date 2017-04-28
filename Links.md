### Language bindings

_NB: those bindings may be more or less maintained, more or less close to the spirit of original API. People who create language bindings sometimes haven't used the C++ API themselves. ImGui was designed for C++ and some of the subtleties may be lost in translation with other languages. If your language supports it, I would suggest replicating the function overloading and default parameters used in the original, else the API may be harder to use. In doubt, always check the original C++ version first!_

cimgui: thin c-api wrapper for ImGui
<br>https://github.com/Extrawurst/cimgui

ImGui.NET: An ImGui wrapper for .NET Core
<br>https://github.com/mellinoe/ImGui.NET

imgui-rs: Rust bindings for ImGui
<br>https://github.com/Gekkio/imgui-rs

DerelictImgui: Dynamic bindings to the cimgui library for the D programming language
<br>https://github.com/Extrawurst/DerelictImgui

CyImGui: Python bindings for ImGui using Cython.
<br>https://github.com/chromy/cyimgui

pyimgui: another Python bindings under development
<br>https://github.com/swistakm/pyimgui

imgui bindings for lua
<br>https://github.com/patrickriordan/imgui_lua_bindings

imgui-chaiscript: ChaiScript bindings for ImGui
<br>https://github.com/JuJuBoSc/imgui-chaiscript

### Framework/engine bindings

Main ImGui repository include examples for DirectX9, DirectX10, DirectX11, OpenGL2/3, Vulkan, Allegro 5, SDL+GL2/3, iOS and Marmalade.
<br>https://github.com/ocornut/imgui/tree/master/examples

Unmerged PR: DirectX12 example (with issues)
<br>https://github.com/ocornut/imgui/pull/301

Unmerged PR: SDL2 + OpenGLES + Emscripten example
<br>https://github.com/ocornut/imgui/pull/336

Unmerged PR: FreeGlut + OpenGL2 example
<br>https://github.com/ocornut/imgui/pull/801

Unmerged PR: Native Win32 and OSX example
<br>https://github.com/ocornut/imgui/pull/281

Unmerged PR: Android Example
<br>https://github.com/ocornut/imgui/pull/421

Cinder backend for dear imgui
<br>https://github.com/simongeilfus/Cinder-ImGui

Flexium/SFML backend for dear imgui (FlexGUI)
<br>https://github.com/DXsmiley/FlexGUI

Irrlicht backend for dear imgui (IrrIMGUI)
<br>https://github.com/ZahlGraf/IrrIMGUI

Unreal Engine 4 backend for dear imgui (UnrealEngine_ImGui)
<br>https://github.com/sronsse/UnrealEngine_ImGui

LÖVE backend for dear imgui
<br>https://github.com/slages/love-imgui

Ogre backend for dear imgui
<br>https://bitbucket.org/LMCrashy/ogreimgui/src

openFrameworks backend for dear imgui (ofxImGui)
<br>https://github.com/jvcleave/ofxImGui

SFML backend for dear imgui
<br>https://github.com/EliasD/imgui-sfml
<br>https://github.com/Mischa-Alff/imgui-backends

fips-imgui: fipsified imgui for fips build system
<br>https://github.com/fungos/fips-imgui

cocos2d-x with imgui
<br>https://github.com/c0i/imguix
<br>https://github.com/ocornut/imgui/issues/551

NanoRT. Raytraced version (!), no GPU (and OpenGL) required. It works on CPU only machine.
<br>https://github.com/syoyo/imgui/tree/nanort/examples/raytrace_example

### Misc

Remote ImGui
<br>https://github.com/JordiRos/remoteimgui

ImWindow: Window and GUI system, include docking/floating window, multi window and multi render support
<br>https://github.com/thennequin/ImWindow

imgui_wm: based on ImWindow above
<br>https://github.com/bkaradzic/bgfx/tree/master/3rdparty/ocornut-imgui

Attempt at rewriting for Java
<br>https://github.com/jovr/imgui

Docking
<br>https://github.com/ocornut/imgui/issues/351

### Articles

OpenGLやDirectXなGUIにimguiが最強すぎる (Japanese)
<br>http://qiita.com/Ushio@github/items/446d78c881334919e156

Using ImGui with modern C++ and STL [...] Part 2. Some tips and tricks.
<br>https://eliasdaler.github.io/using-imgui-with-sfml-pt2