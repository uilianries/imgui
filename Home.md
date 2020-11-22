| Index |
:----------------------------------------------------------: |
| [Discussions](#discussions) - [Wiki Pages](#Wiki-pages) - [Tutorials](#Tutorials) - [References](#References) - [Articles, Videos, etc.](#articles-videos-blog-posts) |

Welcome to the Dear ImGui wiki! Always in construction - feel free to edit and contribute!

Thank you to every past and present [[Sponsors]] for making this project possible.

## Discussions

- [Github Forum](https://github.com/ocornut/imgui/issues/) - for feature requests, bug reports, feedback, code snippets, etc. If you are experienced with Dear ImGui, please consider helping people and answering questions there!
- [Discord Forum](https://discordapp.com/channels/613733622192668672/613733622721019908) / [Discord Invite](https://discord.gg/NgJ4SEP) - if you have issues compiling, linking, running or displaying Dear ImGui (render or inputs, portability issues, using the examples, adding fonts). If you are experienced with Dear ImGui, please consider helping people and answering questions there! 
- It is better to use GitHub: questions and answers will be available to others and you can search for old questions. It is more likely you will receive a correct and detailed answer on GitHub. However, please read the [guidelines](https://github.com/ocornut/imgui/issues/2261) thoroughly before opening a new thread.

## Wiki Pages

- **[[Language bindings, Framework/Engine bindings/backends|Bindings]]**
- **[[FAQ (Frequently Asked Questions)|https://github.com/ocornut/imgui/blob/master/docs/FAQ.md]]**
- **[[Useful widgets gallery|Useful-widgets]]**
- [[Glossary|Glossary]]
- [[Software using dear imgui|Software-using-dear-imgui]]
- [[User quotes|Quotes]]
- [[Help wanted|Help-wanted]]
- [[Incoming work|Incoming-work]]
- [[Tips|Tips]] (for people working _with_ dear imgui)
- [[Developer tips|Developer-Tips]] (for people working _on_ dear imgui)

## Tutorials

- [[Fonts Documentation|https://github.com/ocornut/imgui/blob/master/docs/FONTS.md]]
- [[Image Loading and Displaying Examples|Image-Loading-and-Displaying-Examples]]
- [[Docking|Docking]]
- [[Multi-Viewports|Multi-Viewports]]

## Issues: Some Important Topics

- [#2957](https://github.com/ocornut/imgui/issues/2957) Tables branch available for testing
- [#2109](https://github.com/ocornut/imgui/issues/2109) Docking branch available for testing
- [#1542](https://github.com/ocornut/imgui/issues/1542) Multi-viewports / virtual-viewports feature (in Docking branch)
- [#2117](https://github.com/ocornut/imgui/issues/2117) Linux/Mac compatibility of the multi-viewport branch
- [#3488](https://github.com/ocornut/imgui/issues/3488) Gallery
- [#1713](https://github.com/ocornut/imgui/pull/1713) CMake project to build Examples (PR) by @podsvirov
- Also see https://github.com/ocornut/imgui/labels for categorized issues.

# References

### Useful Widgets

See [[Useful Widgets|Useful-widgets]] page.

### Miscellaneous

- imgui_freetype renderer: [imgui/misc/freetype/](https://github.com/ocornut/imgui/tree/master/misc/freetype) (in main repo)
- Input / IO queue for very low framerate applications: https://gist.github.com/ocornut/8417344f3506790304742b07887adf9f
- Third-party Docking (prior to official docking branch [#2109](https://github.com/ocornut/imgui/issues/2109))
  - [old] @nem0's one (old LumixEngine docking), [github](https://github.com/nem0/LumixEngine/tree/v0.34/external/imgui)
  - [old] @paniq's one (based on @nem0's), [github](https://github.com/ocornut/imgui/issues/351#issuecomment-219775521)
  - [old] @BentleyBlanks's one (based on @paniq's), [github](https://github.com/BentleyBlanks/imguiDock)
  - [old] @thennequin's ImWindow, with OS window managing, [github](https://github.com/thennequin/ImWindow), refactored in bgfx's imgui_wm [github](https://github.com/bkaradzic/bgfx/tree/master/3rdparty/ocornut-imgui)
  - [old] @edin-purkovic's one, [github](https://github.com/edin-purkovic/ImGuiDock)
  - [old] @flix01's one, [github](https://github.com/Flix01/imgui/tree/2015-10-Addons/addons/imguidock)
  - [old] @aoterodelaroza's one, [github](https://github.com/aoterodelaroza/imgui-goodies)

### Building / Packaging Cruft

- CMake https://github.com/ocornut/imgui/pull/1713 (unmerged PR, please send feedback)
- CMake https://github.com/ocornut/imgui/pull/3027  (unmerged PR, please send feedback)
- CMake https://github.com/rokups/imgui/blob/rk/cmake/CMakeLists.txt (self-contained single-file build script)
- Premake5 https://github.com/ocornut/imgui/tree/features/premake5 (unmerged branch)
- Conan https://github.com/bincrafters/conan-imgui, https://bintray.com/bincrafters/public-conan/imgui%3Abincrafters
- Fips (fips-imgui): fipsified imgui for fips build system https://github.com/fungos/fips-imgui
- GN (Chromium, ninja) BUILD.gn file: https://github.com/ndsol/VolcanoSamples/blob/master/src/BUILD.gn

### Example Apps, Framework
(Please also check our [examples/](https://github.com/ocornut/imgui/tree/master/examples) folder in the repo, they work fine as started apps!)

- Starter project for portable app with optional GUI (GLFW/ImGui) https://github.com/abdes/asap
- Bimpy: bundled imgui for python: https://github.com/podgorskiy/bimpy
- giu: Cross platform rapid GUI framework for golang based on Dear ImGui. https://github.com/AllenDang/giu
- imgui_dojo: an easy setup example for imgui https://github.com/LiuZHolmes/imgui_dojo
- mahi-gui: Dirt Simple C++ GUI Toolkit using GLFW, glad, and ImGui https://github.com/mahilab/mahi-gui
- sdl-bgfx-imgui-starter: A starter project for graphics applications https://github.com/pr0g/sdl-bgfx-imgui-starter
- Starter dear-imgui GLFW/OpenGL 3 based CMake C++ project: https://github.com/urddru/imgui-glfw
- Dear PyGui: A Simple Python GUI framework https://github.com/hoffstadt/DearPyGui
- ImDuino (ESP32+TFT+ImSoft+ImGui example): https://github.com/LAK132/ImDuino


### Notable forks

- https://github.com/adobe/imgui
- https://github.com/ubisoftinc/imgui
- https://github.com/mojang/imgui
- https://github.com/flix01/imgui
- https://github.com/Csabix/imgui
- https://github.com/thedmd/imgui

### Related/Suggested Libraries

- stb (stb single-file public domain libraries for C/C++) https://github.com/nothings/stb
- str (lightweight C++ string type with an optional local buffer) https://github.com/ocornut/Str
- nuklear (A single-header ANSI C gui library) https://github.com/Immediate-Mode-UI/Nuklear
- im3d (Immediate mode rendering and 3d gizmos) https://github.com/john-chapman/im3d/projects
- small libraries with minimal dependencies https://github.com/nothings/single_file_libs

## Articles, Videos, Blog Posts

### About the IMGUI paradigm

Dear ImGui is one possible implementation of an idea generally described as the IMGUI (Immediate Mode GUI) paradigm. The Immediate Mode GUI paradigm may at first appear unusual to some users. This is mainly because "Retained Mode" GUIs have been so widespread and predominant. The following links can give you a better understanding about how Immediate Mode GUIs works.
- [Johannes 'johno' Norneby's article](http://www.johno.se/book/imgui.html), 2007.
- [A presentation by Rickard Gustafsson and Johannes Algelind](http://www.cse.chalmers.se/edu/year/2011/course/TDA361/Advanced%20Computer%20Graphics/IMGUI.pdf), 2011.
- [Jari Komppa's tutorial on building an IMGUI library](http://iki.fi/sol/imgui/), 2006.
- [Casey Muratori's original video that popularized the concept](https://mollyrocket.com/861), 2005.
- [Nicolas Guillemot's CppCon'16 flash-talk about Dear ImGui](https://www.youtube.com/watch?v=LSRJ1jZq90k), 2016.
- [Thierry Excoffier's ZMV (Zero Memory Widget)](http://perso.univ-lyon1.fr/thierry.excoffier/ZMW/), 2004.

Another notable uses of IMGUI paradigm include [Unity's own IMGUI widget library](https://docs.unity3d.com/Manual/GUIScriptingGuide.html), often informally referred to as `OnGUI()`, which is used to power the Unity editor and its extensions. This library is unrelated from Dear ImGui (different codebase, design, features and team). The IMGUI library used by Unity has in the past received mixed feedback from its users, presumably because it may have been perceived as a potential candidate for game-facing UI solutions, which it doesn't excel at. However Unity has since provided separate libraries to tackle that case, and their IMGUI library is still very much in use for the Unity Editor and has been its UI backbone for the past 12+ years.

### Articles About Dear ImGui

**English**
- 2016-10: CppCon 2016: Nicolas Guillemot “Dear imgui,": [video](https://www.youtube.com/watch?v=LSRJ1jZq90k).
- 2017-03: Why I think Immediate Mode GUI is way to go for GameDev tools: [post](https://gist.github.com/bkaradzic/853fd21a15542e0ec96f7268150f1b62).
- 2019-06: An introduction to the Dear ImGui library: [blog](https://blog.conan.io/2019/06/26/An-introduction-to-the-Dear-ImGui-library.html).
- 2019-08: Integrating Dear ImGui in a custom Vulkan renderer, https://frguthmann.github.io/posts/vulkan_imgui/
- 2018-04: TheChernoProject: [ImGui in OpenGL](https://www.youtube.com/watch?v=nVaQuNXueFw) / [ImGui Game Engine series](https://www.youtube.com/watch?v=nVaQuNXueFw) / [ImGui Events](https://www.youtube.com/watch?v=yBP1gSbQPPM) / [Docking & Viewport](https://www.youtube.com/watch?v=lZuje-3iyVE)
- 2018-18: C++ DirectX 11 Engine Tutorial 35/36: Set up ImGui: [Part 35](https://www.youtube.com/watch?v=Btx_tujnyB4), [Part 36](https://www.youtube.com/watch?v=o5sJClp0HDY)
- 2018-08: Mana Engine: Thread safety of APIs https://medium.com/@tloch14/mana-engine-thread-safety-of-apis-7e73d482a5c6
- 2016-07: Using imgui with STL types (std::vector) https://eliasdaler.github.io/using-imgui-with-sfml-pt2/#using-imgui-with-stl - Note that `BeginCombo()` api since 1.53 makes it more natural to use all sorts of containers, and since 1.63 you can use InputText() will resizing callbacks (see [imgui_stl.h #2035](https://github.com/ocornut/imgui/issues/2035) for an example with std::string)
- 2019-03: Rust: Making a basic game ui with imgui and ggez http://iolivia.me/posts/imgui-ggez/
- 2019-05: Frictionless Debug UI In C++: [pdf](http://evanachahn.com/Frictionless%20Debug%20UI%20In%20C++.pdf)
- 2020-02: Runtime Compiled C++ Dear ImGui and DX11 Tutorial: [blog](https://www.enkisoftware.com/devlogpost-20200202-1-Runtime-Compiled-C++-Dear-ImGui-and-DirectX11-Tutorial).
- 2020-03: C++ Weekly - Ep 210: Getting Started With SFML & Dear ImGui [youtube](https://www.youtube.com/watch?v=av0SYeUxVMU)
- 2020-03: C++ desktop application with Dear Imgui: [blog](https://ruurdsdevlog.wordpress.com/2020/03/07/c-desktop-application-with-dear-imgui)
- 2020-09: A Vulkan + Dear ImGui Sandbox: [blog](https://tstullich.github.io/posts/vulkan-sandbox/)

**Korean**
- 2018-01: GLFW 사용 방법 정리 (Windows 10, VS2017) https://3dshovel.blogspot.fr/2018/01/glfw-windows-10-visual-studio-2017.html

**Japanese**
- 2016-12: OpenGLやDirectXなGUIにimguiが最強すぎる https://qiita.com/Ushio/items/446d78c881334919e156
- 2016-16: 最強すぎるGUIことImGuiの見た目もイイ感じにする https://qiita.com/izumin5210/items/26eaed69eea2c4318fcd
- 2018-03: ImGuiでデバッグツール http://hikita12312.hatenablog.com/entry/2018/03/17/100535
- 2018-02: OpenSiv3DでImGuiを使う https://qiita.com/RareAmayuki/items/ca802071b452b42ad630
- 2018-12: ダッシュボードオーバーレイ（OpenVR overlay）を作りimguiとDirectXで描いてみる https://qiita.com/ondorela/items/bf4bebf747f90ebf52d8
- 2019-07: imgui で GUI を作るときのメモ https://qiita.com/syoyo/items/85571b0697f1a9cbea71
- 2019-12: Dear ImGuiの使い方まとめ https://qiita.com/mizuma/items/73218dab2f6b022b0227
- 2020-01: imguiのwindowの中で3d cubeの描画をしてやった https://qiita.com/ssaattwworg/items/32ee9a6fdb0476833c02
- 2020-02: imgui 使ってみた https://note.com/onswar/n/nf5bbe6e1e5b3
- 2020-03: Dear ImGui で作成したウィンドウの中に OpenGL で描画するサンプルプログラム https://github.com/tokoik/DrawOpenGLinImGuiWindow

**Chinese (Trad)**
- 2020-10: Day 17 ImGui 元件 https://ithelp.ithome.com.tw/articles/10246595

**French**
- 2020-11: Dear ImGui : une bibliothèque d'interface utilisateur graphique "bloat-free" pour C++ https://cpp.developpez.com/actu/310179

**Polish**
- 2018-01: Szkolenie z biblioteki dear imgui [Video Part 1](https://www.youtube.com/watch?v=TOop9EGngKY) [2](https://www.youtube.com/watch?v=fh6uOdherYw) [3](https://www.youtube.com/watch?v=bF2eOvsX7kY) [4](https://www.youtube.com/watch?v=rcCReEX6h-M) [5](https://www.youtube.com/watch?v=N2Jan6IizbA) [6](https://www.youtube.com/watch?v=70A0YH9h3Ek) [7](https://www.youtube.com/watch?v=0JRaThBx9Ww) [8](https://www.youtube.com/watch?v=O7PVZ6OKDtI) [9](https://www.youtube.com/watch?v=uIp7tLqFzKo), [Slide](https://docs.google.com/presentation/d/1F3jkWkRGCNrCAKi34KXvrkZ9luhS_7RUwHwdYDTFEiY/preview#slide=id.p) 
