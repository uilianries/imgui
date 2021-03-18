Welcome to the Dear ImGui wiki! Feel free to edit and contribute!

Thank you to every past and present [[Sponsors]] for making this project possible.

# Index

- [General](#general)
  - [General documentation](#general-documentation)
  - [Community](#community)
  - [Gallery](#gallery)
  - [Notable branches](#notable-branches)
  - [Demo, Examples](#demo-examples)
  - [Backends, Bindings](#backends-bindings)
  - [Third Party Extensions](#third-party-extensions)
- [Features](#features)
  - [Images](#images)
  - [Fonts/Text](#fonts-text)
  - [Tables](#tables)
  - [Docking](#docking)
  - [Multi-viewports](#multi-viewports)
  - [Inputs](#inputs)
- [Miscellaneous](#Miscellaneous)
  - [Building / Packaging Cruft](#building--packaging-cruft)
  - [Third-party Frameworks](#third-party-frameworks)
  - [Notable forks](#notable-forks)
  - [Ports, Rewrites, Clones](#ports-rewrites-clones)
  - [Related/Suggested Libraries](#relatedsuggested-libraries)
- [Articles, Videos](#articles-videos)
  - [About the IMGUI paradigm](#about-the-imgui-paradigm)
  - [Articles About Dear ImGui](#articles-about-dear-imgui)

----

# General

### General documentation

- [[FAQ (Frequently Asked Questions)|https://github.com/ocornut/imgui/blob/master/docs/FAQ.md]] (docs/FAQ.md)
- [Homepage Readme](https://github.com/ocornut/imgui/blob/master/docs/README.md) (docs/README.md)
- [[Glossary|Glossary]]
- [[Software using Dear ImGui|Software-using-dear-imgui]]
- [[User quotes|Quotes]]
- [[Incoming work|Incoming-work]]
- [[Tips|Tips]] (for people working _with_ dear imgui)
- [[Developer tips|Developer-Tips]] (for people working _on_ dear imgui)
- [Releases / Changelogs](https://github.com/ocornut/imgui/releases) with annotation and pictures.

### Community

- [Github Issues](https://github.com/ocornut/imgui/issues): for feature requests, bug reports, feedback, code snippets, etc. Searching there is recommended as many topics have been discussed and referenced already! Also see [Labels](https://github.com/ocornut/imgui/labels) for categorized issues.
- [Github Discussions](https://github.com/ocornut/imgui/discussions): for questions and anything else.
- [How to open an Issue or Pull Request #2261](https://github.com/ocornut/imgui/issues/2261)
- [[Help wanted|Help-wanted]]

If you are experienced with Dear ImGui, please consider helping people and answering questions!

### Gallery

- [Gallery #3793](https://github.com/ocornut/imgui/issues/3793) Post your screenshots / code here
- [[Useful widgets gallery|Useful-widgets]]

### Notable branches

- [master](https://github.com/ocornut/imgui/tree/master) branch
- [docking](https://github.com/ocornut/imgui/tree/docking) branch (fully maintained): include [Docking](https://github.com/ocornut/imgui/wiki/docking) + [Multi-Viewports](https://github.com/ocornut/imgui/wiki/multi-viewports) features.

### Demo, Examples

- [About Examples apps](https://github.com/ocornut/imgui/blob/master/docs/EXAMPLES.md) (docs/EXAMPLES.md)
- The [examples/](https://github.com/ocornut/imgui/tree/master/examples) folder contains 21 standalone example application for varieties of platforms and frameworks.
- The [imgui_demo.cpp](https://github.com/ocornut/imgui/tree/master/imgui_demo.cpp) file has a `ImGui::ShowDemoWindow()` function which you can call from any imgui-enabled application to showcase variety of features. The demo function is called from all examples/ apps.
- Third-party: @pthom's [imgui_manual](https://pthom.github.io/imgui_manual_online/manual/imgui_manual.html): web version of imgui_demo with interactive browsing of sources.

### Backends, Bindings

- [About Backends](https://github.com/ocornut/imgui/blob/master/docs/BACKENDS.md) (docs/BACKENDS.md)
- The [backends/](https://github.com/ocornut/imgui/tree/master/backends) folder contains 16 reusable backends for varieties of platforms and frameworks.
- [List of language bindings](https://github.com/ocornut/imgui/wiki/Bindings#language-bindings) (C, C#, D, Go,  JavaScript, Lua, Rust and many others)
- [List of engine/framework backends](https://github.com/ocornut/imgui/wiki/Bindings#frameworkengine-bindingsbackends)

### Third-party extensions

- [[List of useful third-party widgets and extensions|Useful-widgets]]

##### [Return to Index](#index)

# Features

### Images

- Tutorial: [[Image Loading and Displaying Examples|Image-Loading-and-Displaying-Examples]]

### Fonts/Text

- Read: [Using Fonts](https://github.com/ocornut/imgui/blob/master/docs/FONTS.md) (docs/FONTS.md)
- Search in Issues: [font/text](https://github.com/ocornut/imgui/issues?q=label%3Afont%2Ftext+)
- Freetype renderer: [imgui_freetype](https://github.com/ocornut/imgui/tree/master/misc/freetype) (misc/freetype/imgui_freetype)

### Tables

- Search in Issues: [tables/columns](https://github.com/ocornut/imgui/issues?q=label%3Atables%2Fcolumns+)
- [#3740](https://github.com/ocornut/imgui/issues/3740) Main Tables Topic

### Docking

- [[About Docking|Docking]]
- Search in Issues: [docking](https://github.com/ocornut/imgui/issues?q=label%3Adocking+)
- [#2109](https://github.com/ocornut/imgui/issues/2109) Main Docking topic
- [List of legacy third-party Docking extensions](https://github.com/ocornut/imgui/wiki/Docking#legacy-third-party-docking-extensions) (prior to official docking: LumixEngine, imguiDock, ImWindow, imgui_wm, etc.)

### Multi-viewports

- [[About Multi-Viewports|Multi-Viewports]]
- Search in Issues: [multi-viewports](https://github.com/ocornut/imgui/issues?q=label%3Amulti-viewports+)
- [#1542](https://github.com/ocornut/imgui/issues/1542) Main Multi-viewports topic
- [#2117](https://github.com/ocornut/imgui/issues/2117) Linux/Mac compatibility of multi-viewports

### Inputs

- Search in Issues: [inputs](https://github.com/ocornut/imgui/issues?q=label%3Ainputs)
- Input / IO queue for very low framerate applications: [gist](https://gist.github.com/ocornut/8417344f3506790304742b07887adf9f)

##### [Return to Index](#index)

# Miscellaneous

### Building / Packaging Cruft

- [#1713](https://github.com/ocornut/imgui/pull/1713) CMake project to build Examples (PR) by @podsvirov (need feedback)
- [#3027](https://github.com/ocornut/imgui/pull/3027) Add CMake configuration (PR) by @Qix- (need feedback)
- [rokups' cmake](https://gist.github.com/rokups/f771217b2d530d170db5cb1e08e9a8f4) Self-contained single-file cmake build script
- Premake5 https://github.com/ocornut/imgui/tree/features/premake5 (unmerged branch)
- Conan [github/bincrafters/conan-imgui](https://github.com/bincrafters/conan-imgui), [bintray/bincrafters/public-conan](https://bintray.com/bincrafters/public-conan/imgui%3Abincrafters)
- Fips (fips-imgui): fipsified imgui for fips build system [github/fungos/fips-imgui](https://github.com/fungos/fips-imgui)
- GN (Chromium, ninja) BUILD.gn file: [github/ndsol/VolcanoSamples](https://github.com/ndsol/VolcanoSamples/blob/master/src/BUILD.gn)

### Third-party Frameworks

(Please also check our [examples/](https://github.com/ocornut/imgui/tree/master/examples) folder in the repo, they work fine as starter apps!)

- asap: Starter project for portable app with optional GUI (GLFW/ImGui) [github/abdes/asap](https://github.com/abdes/asap)
- imgui-app: amalgamation of Dear ImGui and Sokol into two files [github/pplux/imgui-app](https://github.com/pplux/imgui-app)
- Bimpy: bundled imgui for python: [github/podgorskiy/bimpy](https://github.com/podgorskiy/bimpy)
- giu: Cross platform rapid GUI framework for golang based on Dear ImGui. [github/AllenDang/giu](https://github.com/AllenDang/giu)
- Dear PyGui: A Simple Python GUI framework [github/hoffstadt/DearPyGui](https://github.com/hoffstadt/DearPyGui)
- imgui_dojo: an easy setup example for imgui [github/LiuZHolmes/imgui_dojo](https://github.com/LiuZHolmes/imgui_dojo)
- mahi-gui: Dirt Simple C++ GUI Toolkit using GLFW, glad, and ImGui [github/mahilab/mahi-gui](https://github.com/mahilab/mahi-gui)
- sdl-bgfx-imgui-starter: A starter project for graphics applications [github/pr0g/sdl-bgfx-imgui-starter](https://github.com/pr0g/sdl-bgfx-imgui-starter)
- Starter dear-imgui GLFW/OpenGL 3 based CMake C++ project: [github/urddru/imgui-glfw](https://github.com/urddru/imgui-glfw)
- ImDuino (ESP32+TFT+ImSoft+ImGui example): [github/LAK132/ImDuino](https://github.com/LAK132/ImDuino)
- ImFrame: Dear ImGui + GLFW C++ / CMake application framework: [github/JamesBoer/ImFrame](https://github.com/JamesBoer/ImFrame)

### Notable forks

- https://github.com/adobe/imgui
- https://github.com/ubisoftinc/imgui
- https://github.com/mojang/imgui
- https://github.com/thedmd/imgui
- https://github.com/flix01/imgui
- https://github.com/Csabix/imgui

### Ports, Rewrites, Clones

- See: [Ports, Rewrites, Clones](https://github.com/ocornut/imgui/wiki/Bindings#ports-rewrites-clones) section.

### Related/Suggested Libraries

- stb (stb single-file public domain libraries for C/C++) https://github.com/nothings/stb
- str (lightweight C++ string type with an optional local buffer) https://github.com/ocornut/Str
- nuklear (A single-header ANSI C gui library) https://github.com/Immediate-Mode-UI/Nuklear
- im3d (Immediate mode rendering and 3d gizmos) https://github.com/john-chapman/im3d/projects
- An immediate mode 3D gizmo (translation, rotation, scale for scene editing) https://github.com/meshula/tinygizmo
- small libraries with minimal dependencies https://github.com/nothings/single_file_libs

##### [Return to Index](#index)

# Articles, Videos

### About the IMGUI paradigm

Dear ImGui is one possible implementation of an idea generally described as the IMGUI (Immediate Mode GUI) paradigm. The Immediate Mode GUI paradigm may at first appear unusual to some users. This is mainly because "Retained Mode" GUIs have been so widespread and predominant. The following links can give you a better understanding about how Immediate Mode GUIs works.
- [[Wiki page About the IMGUI paradigm|About-the-IMGUI-paradigm]]
- [Johannes 'johno' Norneby's article](http://www.johno.se/book/imgui.html), 2007.
- [A presentation by Rickard Gustafsson and Johannes Algelind](http://www.cse.chalmers.se/edu/year/2011/course/TDA361/Advanced%20Computer%20Graphics/IMGUI.pdf), 2011.
- [Jari Komppa's tutorial on building an IMGUI library](http://iki.fi/sol/imgui/), @jarikomppa, 2006.
- [Casey Muratori's original video that popularized the concept](https://mollyrocket.com/861), 2005.
- [Writing an IMGUI](https://www.youtube.com/watch?v=wsJ8Y1HO250), @heroseh, 2021
- [Nicolas Guillemot's CppCon'16 flash-talk about Dear ImGui](https://www.youtube.com/watch?v=LSRJ1jZq90k), 2016.
- [Thierry Excoffier's ZMV (Zero Memory Widget)](http://perso.univ-lyon1.fr/thierry.excoffier/ZMW/), 2004.

Another notable uses of IMGUI paradigm include [Unity's own IMGUI widget library](https://docs.unity3d.com/Manual/GUIScriptingGuide.html), often informally referred to as `OnGUI()`, which is used to power the Unity editor and its extensions. This library is unrelated from Dear ImGui (different codebase, design, features and team). The IMGUI library used by Unity has in the past received mixed feedback from its users, presumably because it may have been perceived as a potential candidate for game-facing UI solutions, which it doesn't excel at. However Unity has since provided separate libraries to tackle that case, and their IMGUI library is still very much in use for the Unity Editor and has been its UI backbone for the past 12+ years.

### Articles About Dear ImGui

**English**
- 2016-07: Using imgui with STL types (std::vector) https://eliasdaler.github.io/using-imgui-with-sfml-pt2/#using-imgui-with-stl - Note that BeginCombo() api since 1.53 makes it more natural to use all sorts of containers, and since 1.63 you can use InputText() will resizing callbacks (see [imgui_stdlib.h #2035](https://github.com/ocornut/imgui/issues/2035) for an example with std::string), so most of that article is outdated.
- 2016-10: CppCon 2016: Nicolas Guillemot “Dear imgui,": [video](https://www.youtube.com/watch?v=LSRJ1jZq90k).
- 2017-03: Why I think Immediate Mode GUI is way to go for GameDev tools: [post](https://gist.github.com/bkaradzic/853fd21a15542e0ec96f7268150f1b62).
- 2018-04: TheChernoProject: [ImGui in OpenGL](https://www.youtube.com/watch?v=nVaQuNXueFw) / [ImGui Game Engine series](https://www.youtube.com/watch?v=st4lgNI6_F4) / [ImGui Events](https://www.youtube.com/watch?v=yBP1gSbQPPM) / [Docking & Viewport](https://www.youtube.com/watch?v=lZuje-3iyVE)
- 2018-08: Mana Engine: Thread safety of APIs [medium/tloch34](https://medium.com/@tloch14/mana-engine-thread-safety-of-apis-7e73d482a5c6)
- 2018-10: C++ DirectX 11 Engine Tutorial 35/36: Set up ImGui: [Part 35](https://www.youtube.com/watch?v=Btx_tujnyB4), [Part 36](https://www.youtube.com/watch?v=o5sJClp0HDY)
- 2019-01: Could ImGUI be the future of GUIs? [games.greggman.com](https://games.greggman.com/game/imgui-future/)
- 2019-03: Rust: Making a basic game ui with imgui and ggez [blog](http://iolivia.me/posts/imgui-ggez)
- 2019-05: Frictionless Debug UI In C++: [pdf](http://evanachahn.com/Frictionless%20Debug%20UI%20In%20C++.pdf)
- 2019-06: An introduction to the Dear ImGui library: [blog](https://blog.conan.io/2019/06/26/An-introduction-to-the-Dear-ImGui-library.html).
- 2019-08: Integrating Dear ImGui in a custom Vulkan renderer [blog](https://frguthmann.github.io/posts/vulkan_imgui/)
- 2020-02: Runtime Compiled C++ Dear ImGui and DX11 Tutorial: [blog](https://www.enkisoftware.com/devlogpost-20200202-1-Runtime-Compiled-C++-Dear-ImGui-and-DirectX11-Tutorial).
- 2020-03: C++ Weekly - Ep 210: Getting Started With SFML & Dear ImGui [youtube](https://www.youtube.com/watch?v=av0SYeUxVMU)
- 2020-03: C++ desktop application with Dear Imgui: [blog](https://ruurdsdevlog.wordpress.com/2020/03/07/c-desktop-application-with-dear-imgui)
- 2020-09: A Vulkan + Dear ImGui Sandbox: [blog](https://tstullich.github.io/posts/vulkan-sandbox/)
- 2021-01: Gamefromscratch: Dear ImGui C++ GUI Framework For AAA Games and Game Engines [youtube](https://www.youtube.com/watch?v=Du--cH01ZWI)
- 2021-02: Introduction to the Dear ImGui C++ Library with Conan: [video](https://www.youtube.com/watch?v=O2E-W9P-jKc), [blog](https://blog.conan.io/2019/06/26/An-introduction-to-the-Dear-ImGui-library.html)

**Korean**
- 2018-01: GLFW 사용 방법 정리 (Windows 10, VS2017) [3dshovel.blogspot.com](https://3dshovel.blogspot.com/2018/01/glfw-windows-10-visual-studio-2017.html)

**Japanese**
- 2016-12: OpenGLやDirectXなGUIにimguiが最強すぎる [qiita.com/Ushio](https://qiita.com/Ushio/items/446d78c881334919e156)
- 2016-16: 最強すぎるGUIことImGuiの見た目もイイ感じにする [qiita.com/izumin5210](https://qiita.com/izumin5210/items/26eaed69eea2c4318fcd)
- 2018-03: ImGuiでデバッグツール [hikita12312.hatenablog.com](http://hikita12312.hatenablog.com/entry/2018/03/17/100535)
- 2018-02: OpenSiv3DでImGuiを使う [qiita.com/RareAmayuki](https://qiita.com/RareAmayuki/items/ca802071b452b42ad630)
- 2018-12: ダッシュボードオーバーレイ（OpenVR overlay）を作りimguiとDirectXで描いてみる [qiita.com/ondorela](https://qiita.com/ondorela/items/bf4bebf747f90ebf52d8)
- 2019-07: imgui で GUI を作るときのメモ [qiita.com/syoyo](https://qiita.com/syoyo/items/85571b0697f1a9cbea71)
- 2019-12: Dear ImGuiの使い方まとめ [qiita.com/mizuma](https://qiita.com/mizuma/items/73218dab2f6b022b0227)
- 2020-01: imguiのwindowの中で3d cubeの描画をしてやった [qiita.com/ssaattwworg](https://qiita.com/ssaattwworg/items/32ee9a6fdb0476833c02)
- 2020-02: imgui 使ってみた [note.com/onswar](https://note.com/onswar/n/nf5bbe6e1e5b3)
- 2020-03: Dear ImGui で作成したウィンドウの中に OpenGL で描画するサンプルプログラム [github/tokoik](https://github.com/tokoik/DrawOpenGLinImGuiWindow)
- 2020-12: OpenSiv3Dで自作したImGuiライクなGUIライブラリの紹介 [qiita.com/sthairno](https://qiita.com/sthairno/items/edfb969a4d8f51f57a2a)
- 2020-12:【UE4】GUIフレームワーク「Dear ImGui」を使ってデバッグ・ツール用UIを作ってみよう！[pafuhana1213.hatenablog.com](https://pafuhana1213.hatenablog.com/entry/UnrealImGui-HowTo-Basic)
- 2020-12:【UE4】【C++】ImGuiを使ってみてハマった所、気付いた所 [toofu0.hatenablog.com](https://toofu0.hatenablog.com/entry/2020/12/18/014706)
- 2021-03: UE4：ImGui導入手順 [toncrimentan-w.hatenablog.com](https://toncrimentan-w.hatenablog.com/entry/2021/03/08/154022)

**Chinese (Trad)**
- 2020-10: Day 17 ImGui 元件 [ithelp.ithome.com.tw](https://ithelp.ithome.com.tw/articles/10246595)

**French**
- 2020-11: Dear ImGui : une bibliothèque d'interface utilisateur graphique "bloat-free" pour C++ [cpp.developpez.com](https://cpp.developpez.com/actu/310179)

**Polish**
- 2018-01: Szkolenie z biblioteki dear imgui [Video Part 1](https://www.youtube.com/watch?v=TOop9EGngKY) [2](https://www.youtube.com/watch?v=fh6uOdherYw) [3](https://www.youtube.com/watch?v=bF2eOvsX7kY) [4](https://www.youtube.com/watch?v=rcCReEX6h-M) [5](https://www.youtube.com/watch?v=N2Jan6IizbA) [6](https://www.youtube.com/watch?v=70A0YH9h3Ek) [7](https://www.youtube.com/watch?v=0JRaThBx9Ww) [8](https://www.youtube.com/watch?v=O7PVZ6OKDtI) [9](https://www.youtube.com/watch?v=uIp7tLqFzKo), [Slide](https://docs.google.com/presentation/d/1F3jkWkRGCNrCAKi34KXvrkZ9luhS_7RUwHwdYDTFEiY/preview#slide=id.p) 

##### [Return to Index](#index)
