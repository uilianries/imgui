Welcome to the Dear ImGui wiki! Feel free to edit and contribute!

# Index

- [General](#general)
  - [General documentation](#general-documentation)
  - [Community](#community)
  - [Demo, Examples](#demo-examples)
  - **[Language Bindings](#language-bindings)**
  - **[Platform and Rendering Backends](#platform-and-rendering-backends)**
  - **[Third-Party Extensions](#third-party-extensions)**
  - **[Testing / Automation](#testing--automation)**
  - [Gallery](#gallery)
  - [Notable branches](#notable-branches)
- [Features](#features)
  - [Debug Tools](#debug-tools)
  - [Images](#images)
  - [Fonts/Text](#fontstext)
  - [Tables](#tables)
  - [Docking](#docking)
  - [Multi-viewports](#multi-viewports)
  - [Inputs](#inputs)
- [Miscellaneous](#Miscellaneous)
  - [Building / Packaging Cruft](#building--packaging-cruft)
  - [Third-party Frameworks, Templates](#third-party-frameworks-templates)
  - [Notable forks](#notable-forks)
  - [Ports, Rewrites, Clones](#ports-rewrites-clones)
  - [Related/Suggested Libraries](#relatedsuggested-libraries)
  - [Job Board](#job-board)
- [Articles, Videos](#articles-videos)
  - [Articles/Videos About Dear ImGui](#articlesvideos-about-dear-imgui)
  - [About the IMGUI paradigm](#about-the-imgui-paradigm)

----

# General

### General documentation

- [[FAQ (Frequently Asked Questions)|https://github.com/ocornut/imgui/blob/master/docs/FAQ.md]] (docs/FAQ.md)
- [Homepage Readme](https://github.com/ocornut/imgui/blob/master/docs/README.md) (docs/README.md)
- [[Glossary|Glossary]]
- [[Software using Dear ImGui|Software-using-dear-imgui]]
- [[User quotes|Quotes]]
- [[Upcoming changes|Upcoming-changes]] (~roadmap)
- [[Tips|Tips]] (for people working _with_ dear imgui)
- [[Developer tips|Developer-Tips]] (for people working _on_ dear imgui)
- [Releases / Changelogs](https://github.com/ocornut/imgui/releases) with annotations and pictures.
- Interactive/web [imgui_manual](https://pthom.github.io/imgui_manual_online/manual/imgui_manual.html) by @pthom

### Community

- [Github Issues](https://github.com/ocornut/imgui/issues): for feature requests, bug reports, feedback, code snippets, etc. Searching there is recommended as many topics have been discussed and referenced already! Also see [Labels](https://github.com/ocornut/imgui/labels) for categorized issues.
- [How to open an Issue or Pull Request #2261](https://github.com/ocornut/imgui/issues/2261)
- [[Help wanted|Help-wanted]]

### Demo, Examples

- [About Examples apps](https://github.com/ocornut/imgui/blob/master/docs/EXAMPLES.md) (docs/EXAMPLES.md)
- The [examples/](https://github.com/ocornut/imgui/tree/master/examples) folder contains 23 standalone example applications for varieties of platforms and frameworks.
- The [imgui_demo.cpp](https://github.com/ocornut/imgui/tree/master/imgui_demo.cpp) file has a `ImGui::ShowDemoWindow()` function which you can call from any imgui-enabled application to showcase variety of features. The demo function is called from all examples/ apps.
- Third-party: @pthom's [imgui_manual](https://pthom.github.io/imgui_manual_online/manual/imgui_manual.html): web version of imgui_demo with interactive browsing of sources.

### Language Bindings

- [List of language bindings](https://github.com/ocornut/imgui/wiki/Bindings) (C, C#, D, Go, JavaScript, Lua, Python, Rust and many others...)
- [List of binding generators](https://github.com/ocornut/imgui/wiki/Bindings#binding-generators) (cimgui, dear_bindings)

### Platform and Rendering Backends

- [List of engine/framework backends](https://github.com/ocornut/imgui/wiki/Bindings#frameworkengine-backends) (Unity, Unreal and many others...)
- [About Backends](https://github.com/ocornut/imgui/blob/master/docs/BACKENDS.md) (docs/BACKENDS.md)
- The [backends/](https://github.com/ocornut/imgui/tree/master/backends) folder contains 18 reusable backends for varieties of platforms and frameworks.

### Third-party extensions

- [[List of useful third-party extensions/widgets|Useful-Extensions]] (text editors, node editors, plotting/graphing, curves/animations/gradients editors, knobs, spinners, remoting, 3d gizmos and many more!)

### Testing / Automation

- See [imgui_test_engine](https://github.com/ocornut/imgui_test_engine): Dear ImGui Test Engine + Dear ImGui Test Suite

### Gallery

- [Gallery #6478](https://github.com/ocornut/imgui/issues/6478) Post your screenshots / code here
- [[Useful extensions/widgets gallery|Useful-extensions]]

### Notable branches

- [master](https://github.com/ocornut/imgui/tree/master) branch
- [docking](https://github.com/ocornut/imgui/tree/docking) branch (fully maintained): include [Docking](https://github.com/ocornut/imgui/wiki/docking) + [Multi-Viewports](https://github.com/ocornut/imgui/wiki/multi-viewports) features.

##### [Return to Index](#index)

# Features

### Debug Tools

- See [[Debug Tools|Debug-Tools]] wiki page explaining `ShowMetricsWindow()`, `ShowDebugLogWindow()`, `ShowStackToolWindow()`, Item Picker..

### Images

- Tutorial: [[Image Loading and Displaying Examples|Image-Loading-and-Displaying-Examples]] (helpful if you are confused about `ImTextureID`).

### Fonts/Text

- Read: [Using Fonts](https://github.com/ocornut/imgui/blob/master/docs/FONTS.md) (docs/FONTS.md)
- Search in Issues: [font/text](https://github.com/ocornut/imgui/issues?q=label%3Afont%2Ftext+)
- Freetype renderer: [imgui_freetype](https://github.com/ocornut/imgui/tree/master/misc/freetype) (misc/freetype/imgui_freetype)

### Tables

- [#3740](https://github.com/ocornut/imgui/issues/3740) Main Tables Topic
- Search in Issues: [tables/columns](https://github.com/ocornut/imgui/issues?q=label%3Atables%2Fcolumns+)

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
- 1.87 new IO event queue API [#4921](https://github.com/ocornut/imgui/issues/4921)
- ~~Input / IO queue for very low framerate applications: [gist](https://gist.github.com/ocornut/8417344f3506790304742b07887adf9f)~~

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

### Third-party Frameworks, Templates

(Please also check our [examples/](https://github.com/ocornut/imgui/tree/master/examples) folder in the repo, they work fine as starter apps!)

C/C++, Python:
- imgui_bundle: bundle including various powerful libraries [...] easily create ImGui applications in C++ and Python, under Windows, macOS, and Linux [github/pthom/imgui_bundle](https://github.com/pthom/imgui_bundle)

C/C++
- asap: Starter project for portable app with optional GUI (GLFW/ImGui) [github/abdes/asap](https://github.com/abdes/asap)
- GGWeb: Template for making a GUI app with C++ / Dear ImGui / SDL / OpenGL / Emscripten that can run both natively and in the browser. [github/ggerganov/ggweb](https://github.com/ggerganov/ggweb)
- Walnut: simple application framework for Vulkan and Dear ImGui apps. [github/TheCherno/Walnut](https://github.com/TheCherno/Walnut)
- imgui-app: amalgamation of Dear ImGui and Sokol into two files [github/pplux/imgui-app](https://github.com/pplux/imgui-app)
- imgui_application: Tiny library for making c++ imgui-based apps (web & native) [github/inobelar/imgui_application](https://github.com/inobelar/imgui_application)
- imgui_dojo: an easy setup example for imgui [github/LiuZHolmes/imgui_dojo](https://github.com/LiuZHolmes/imgui_dojo)
- mahi-gui: Dirt Simple C++ GUI Toolkit using GLFW, glad, and ImGui [github/mahilab/mahi-gui](https://github.com/mahilab/mahi-gui)
- sdl-bgfx-imgui-starter: A starter project for graphics applications [github/pr0g/sdl-bgfx-imgui-starter](https://github.com/pr0g/sdl-bgfx-imgui-starter)
- Starter dear-imgui GLFW/OpenGL 3 based CMake C++ project: [github/urddru/imgui-glfw](https://github.com/urddru/imgui-glfw)
- ImDuino (ESP32+TFT+ImSoft+ImGui example): [github/LAK132/ImDuino](https://github.com/LAK132/ImDuino)
- ImFrame: Dear ImGui + GLFW C++ / CMake application framework: [github/JamesBoer/ImFrame](https://github.com/JamesBoer/ImFrame)

Other:
- ImTemplate: Template for making a single-windowed (or not) Dear ImGui application in Nim. [github/Patitotective/ImTemplate](https://github.com/Patitotective/ImTemplate)
- Bimpy: bundled imgui for python: [github/podgorskiy/bimpy](https://github.com/podgorskiy/bimpy)
- giu: Cross platform rapid GUI framework for golang based on Dear ImGui. [github/AllenDang/giu](https://github.com/AllenDang/giu)
- Dear PyGui: A Simple Python GUI framework [github/hoffstadt/DearPyGui](https://github.com/hoffstadt/DearPyGui)
- ImGui Javascript Sandbox: [web](https://codepen.io/flyovergames/pen/xYPBaj)

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
- egui (egui: an easy-to-use immediate mode GUI in Rust) https://github.com/emilk/egui
- im3d (Immediate mode rendering and 3d gizmos) https://github.com/john-chapman/im3d
- An immediate mode 3D gizmo (translation, rotation, scale for scene editing) https://github.com/meshula/tinygizmo
- small libraries with minimal dependencies https://github.com/nothings/single_file_libs

##### [Return to Index](#index)

### Job Board

See https://github.com/ocornut/imgui/issues/5031 for industry job offers relating to use of Dear ImGui.

# Articles, Videos

### Articles/Videos About Dear ImGui

**English**
- 2016-07: Using imgui with STL types [blog](https://eliasdaler.github.io/using-imgui-with-sfml-pt2/#using-imgui-with-stl) _[note that this article is now outdated: BeginCombo() api makes it natural to enumerate from any containers, InputText() supports resizing callbacks and [imgui_stdlib.h](https://github.com/ocornut/imgui/tree/master/misc/cpp) provides wrapper for std::string]_
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
- 2021-04: Thinking in Immediate: [video](https://www.youtube.com/watch?v=a1VLfd3RpCk)
- 2021-05: ImGui-SFML: Using CMake and managing dependencies: [blog](https://eliasdaler.github.io/using-cmake/)
- 2021-05: ImGui + GLFW Tutorial: [video](https://www.youtube.com/watch?v=VRwhNKoxUtk)
- 2022-02: BEST WAY to make Desktop Applications in C++: [video](https://www.youtube.com/watch?v=vWXrFetSH8w)
- 2022-04: Make your own GUI apps in C++ (with Dear ImGui and Vulkan) [video](https://www.youtube.com/watch?v=5zS-DZhCA2g)
- 2022-05: Dear ImGui in Unreal Engine 5 with C++ [video](https://www.youtube.com/watch?v=qyO38jX5RU8) + [followup](https://www.youtube.com/watch?v=oS1vLHA3_jw)
- 2023-02: Dear ImGui for Unity - easiest GUI menus and bars [video](https://www.youtube.com/watch?v=i9yjuJC11zU)

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
- 2022-07: ImGui で日本語と記号♥と絵文字😺の表示 [zenn.dev/tenka](https://zenn.dev/tenka/articles/display_japanese_symbols_and_emoji_with_imgui)
- 2022-11:【Unity】Dear ImGuiの導入方法 [limegame.hatenablog](https://limegame.hatenablog.com/entry/2022/11/11/131111) +【Unity】Dear ImGuiのメニューバー実装方法 [limegame.hatenablog](https://limegame.hatenablog.com/entry/2022/11/21/153547)
- 2023-01: Java 3D LWJGL 改造 〜Chapter10：Imgui を使用した GUI 描画を改造〜 [zenryokuservice.com](https://zenryokuservice.com/wp/2023/01/03/java-3d-lwjgl-%e6%94%b9%e9%80%a0-%e3%80%9cchapter10%ef%bc%9aimgui-%e3%82%92%e4%bd%bf%e7%94%a8%e3%81%97%e3%81%9f-gui-%e6%8f%8f%e7%94%bb%e3%82%92%e6%94%b9%e9%80%a0%e3%80%9c/)
- 2023-03: DirectX12でImGuiを使用する [zenn.dev/norainu](https://zenn.dev/norainu/articles/10856bfe120aa2)

**Chinese (Trad)**
- 2020-10: Day 17 ImGui 元件 [ithelp.ithome.com.tw](https://ithelp.ithome.com.tw/articles/10246595)
- 2022-11:【ImGui 入门到精通  课程介绍】 [video](https://www.bilibili.com/video/BV13e4y1m73N/?share_source=copy_web&vd_source=f1c007c0c824bfae9d1cc94d21fada0d)

**French**
- 2020-11: Dear ImGui : une bibliothèque d'interface utilisateur graphique "bloat-free" pour C++ [cpp.developpez.com](https://cpp.developpez.com/actu/310179)

**German**
- 2023-04: Interaktive GUI mit C++ und ImGui: Praktische Beispiele [udemy.com/course](https://www.udemy.com/course/interaktive-gui-mit-c-und-imgui-praktische-beispiele/)

**Portuguese**
- 2022-05: Como Criar Interfaces Gráficas com Dear ImGui e SFML [video](https://www.youtube.com/watch?v=XmiEkoqodcg)

**Polish**
- 2018-01: Szkolenie z biblioteki dear imgui [Video Part 1](https://www.youtube.com/watch?v=TOop9EGngKY) [2](https://www.youtube.com/watch?v=fh6uOdherYw) [3](https://www.youtube.com/watch?v=bF2eOvsX7kY) [4](https://www.youtube.com/watch?v=rcCReEX6h-M) [5](https://www.youtube.com/watch?v=N2Jan6IizbA) [6](https://www.youtube.com/watch?v=70A0YH9h3Ek) [7](https://www.youtube.com/watch?v=0JRaThBx9Ww) [8](https://www.youtube.com/watch?v=O7PVZ6OKDtI) [9](https://www.youtube.com/watch?v=uIp7tLqFzKo), [Slide](https://docs.google.com/presentation/d/1F3jkWkRGCNrCAKi34KXvrkZ9luhS_7RUwHwdYDTFEiY/preview#slide=id.p) 
- 2021-02: Dear ImGui: pragmatyczne podejście do programowania interfejsów użytkownika [programista mag](https://programistamag-pl.translate.goog/programista-1-2021-95/?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=pl&_x_tr_pto=wapp)

### About the IMGUI paradigm

Dear ImGui is one possible implementation of an idea generally described as the IMGUI (Immediate Mode GUI) paradigm. The Immediate Mode GUI paradigm may at first appear unusual to some users. This is mainly because "Retained Mode" GUIs have been so widespread and predominant. The following links can give you a better understanding about how Immediate Mode GUIs works.
- **[[Our Wiki page About the IMGUI paradigm|About-the-IMGUI-paradigm]]**.
- [Johannes 'johno' Norneby's article](http://www.johno.se/book/imgui.html), 2007.
- [A presentation by Rickard Gustafsson and Johannes Algelind](http://www.cse.chalmers.se/edu/year/2011/course/TDA361/Advanced%20Computer%20Graphics/IMGUI.pdf), 2011.
- [Jari Komppa's tutorial on building an IMGUI library](http://iki.fi/sol/imgui/), @jarikomppa, 2006.
- [Casey Muratori's original video that popularized the concept](https://mollyrocket.com/861), 2005.
  - [First notable post by Casey on 2005-07-05](https://web.archive.org/web/20070824213736/http://www.mollyrocket.com/forums/viewtopic.php?t=134&start=0&sid=cb913629aa8310947c0476848a8824dd). 
  - [2007 Mirror of Molly Rocket's IMGUI forums](https://web.archive.org/web/20070824203105/http://www.mollyrocket.com/forums/viewforum.php?f=10&sid=9680eeedbe87034741d936cbfe319f57) (with posts).
  - [2013 Mirror of Molly Rocket's IMGUI forums](https://web.archive.org/web/20131221233224/http://mollyrocket.com/forums/viewforum.php?f=10&sid=b7ce0b0de4493f63edd88d13c99501a9) (index only, missing posts).
- [Sean Barrett's article in Game Developer Magazine](https://archive.org/details/GDM_September_2005) (Page 34), September 2005.
- [Sean Barrett's IMGUI page and toolkit](http://silverspaceship.com/inner/imgui), @nothings, 2005.
- [Nicolas Guillemot's CppCon'16 flash-talk about Dear ImGui](https://www.youtube.com/watch?v=LSRJ1jZq90k), 2016.
- [Thierry Excoffier's ZMV (Zero Memory Widget)](http://perso.univ-lyon1.fr/thierry.excoffier/ZMW/), 2004.

Another notable uses of IMGUI paradigm include [Unity's own IMGUI widget library](https://docs.unity3d.com/Manual/GUIScriptingGuide.html), often informally referred to as `OnGUI()`, which powers the Unity editor and its extensions. This library is unrelated from Dear ImGui. The IMGUI library used by Unity has in the past received mixed feedback from its users, presumably because it may have been perceived as a potential candidate for game-facing UI solutions, which it doesn't excel at. However Unity has since provided separate libraries to tackle that case, and their IMGUI library is still very much in use for the Unity Editor and has been its UI backbone for the past 15+ years.

##### [Return to Index](#index)
