| Index |
:----------------------------------------------------------: |
| [Discussions](#discussions) - [Wiki Pages](#Wiki-pages) - [Tutorials](#Tutorials) - [Useful Widgets & References](#Useful-widgets--references) - [Articles, Videos, etc.](#articles-videos-blog-posts) |

Welcome to the Dear ImGui wiki!
This wiki is in construction.
Feel free to edit and contribute!

## Discussions

- [Github Forum](https://github.com/ocornut/imgui/issues/) - for feature requests, bug reports, feedback, code snippets, etc. If you are experienced with Dear ImGui, please consider helping people and answering questions there!
- [Discord Forum](https://discordapp.com/channels/613733622192668672/613733622721019908) / [Discord Invite](https://discord.gg/NgJ4SEP) - if you have issues compiling, linking, running or displaying Dear ImGui (render or inputs, portability issues, using the examples, adding fonts). If you are experienced with Dear ImGui, please consider helping people and answering questions there! 
- It is better to use GitHub: questions and answers will be available to others and you can search for old questions. It is more likely you will receive a correct and detailed answer on GitHub. However, please read the [guidelines](https://github.com/ocornut/imgui/issues/2261) thoroughly before opening a new thread.

## Wiki Pages

- **[[Language bindings, Framework/Engine bindings|Bindings]]**
- [[FAQ (Frequently Asked Questions)|https://github.com/ocornut/imgui/blob/master/docs/FAQ.md]]
- [[Glossary|Glossary]]
- [[Software using dear imgui|Software-using-dear-imgui]]
- [[User quotes|Quotes]]
- [[Help wanted|Help-wanted]]
- [[Incoming work|Incoming-work]]
- [[Sponsors|Sponsors]]
- [[Tips|Tips]] (for people working _with_ dear imgui)
- [[Developer tips|Developer-Tips]] (for people working _on_ dear imgui)

## Tutorials

- [[Image Loading and Displaying Examples|Image-Loading-and-Displaying-Examples]]
- [[Font Loading Example|Loading-Font-Example]]

## Issues: Some Important Topics

- [#2109](https://github.com/ocornut/imgui/issues/2109) Docking branch available for testing
- [#1542](https://github.com/ocornut/imgui/issues/1542) Multi-viewports / virtual viewports Branch
- [#2117](https://github.com/ocornut/imgui/issues/2117) Linux/Mac compatibility of the multi-viewport branch
- [#2265](https://github.com/ocornut/imgui/issues/2529) Gallery
- [#1713](https://github.com/ocornut/imgui/pull/1713) CMake project to build Examples (PR) by @podsvirov
- Also see https://github.com/ocornut/imgui/labels for categorized issues.

# Useful Widgets & References

### Text Editors

- ImGuiColorTextEdit: Colorizing text editor for ImGui [[github](https://github.com/BalazsJako/ImGuiColorTextEdit)]
- Zep: An embeddable editor, with optional support for using vim keystrokes. [[github](https://github.com/cmaughan/zep)]
- Scintilla integration [[thread](https://github.com/ocornut/imgui/issues/108)]

### Node Editors

- imgui-node-editor: https://github.com/thedmd/imgui-node-editor
- rokups/ImNodes: https://github.com/rokups/ImNodes
- Nelarius/imnodes: https://github.com/Nelarius/imnodes
- Many more in this thread: https://github.com/ocornut/imgui/issues/306

### Curves, Animations, Gradients

- Bezier widget (@r-lyeh) https://github.com/ocornut/imgui/issues/786
- ImSequencer (animation sequencer) https://github.com/CedricGuillemet/ImGuizmo
- Gradient color generator (@galloscript): https://gist.github.com/galloscript/8a5d179e432e062550972afcd1ecf112

### Plotting, Graph

- imgui-plot (@soulthreads): https://github.com/soulthreads/imgui-plot and [#2747](https://github.com/ocornut/imgui/issues/2747)
- Flame graph widget: https://github.com/ocornut/imgui/issues/2859
- Plot var helper: [[plot_var_example]]

### File Browsers

- File browser: https://github.com/AirGuanZ/imgui-filebrowser
- File browser: https://github.com/gallickgunner/ImGui-Addons
- File browser: https://github.com/Flix01/imgui/wiki/ImGui-Addons-Branch-Home
- File browser: https://github.com/aiekick/ImGuiFileDialog

### Rich text

- Markdown: https://github.com/juliettef/imgui_markdown
- URL/Links: https://gist.github.com/dougbinks/ef0962ef6ebe2cadae76c4e9f0586c69#file-imguiutils-h-L228-L262

### Misc

- Memory Editor: [imgui_club/imgui_memory_editor/](https://github.com/ocornut/imgui_club/tree/master/imgui_memory_editor)
- ImGuizmo (3d translation/rotation Gizmo) https://github.com/CedricGuillemet/ImGuizmo
- imGuiZMO.quat (3d translation/rotation Gizmo) https://github.com/BrutPitt/imGuIZMO.quat
- Splitters: https://github.com/ocornut/imgui/issues/319
- Spinner + Loading Bar progress indicators: https://github.com/ocornut/imgui/issues/1901
- ImHotKey (Hotkey Editor): https://github.com/CedricGuillemet/ImHotKey
- IP Entry Box (@adam4813) https://github.com/ocornut/imgui/issues/388
- Pie menu test: https://github.com/ocornut/imgui/issues/434
- Knobs: https://github.com/ocornut/imgui/issues/942#issuecomment-268369298
- Toggle Button: https://github.com/ocornut/imgui/issues/1537
- ImGui::Auto(): leverage C++17 to serialize any structure into imgui interfaces https://github.com/Csabix/imgui/tree/master/auto
- LayoutWidget #2779 https://github.com/xpenatan/jDear-imgui/tree/master/extensions/imgui-layout-widget
- Issues "useful widgets" Tag: https://github.com/ocornut/imgui/labels/useful%20widgets

### Third party repos

- @flix01's addons: [ImGui-Addons-Branch-Home](https://github.com/Flix01/imgui/wiki/ImGui-Addons-Branch-Home) for instructions and [github repo](https://github.com/Flix01/imgui) for code.
  - file dialog, date picker, listview, toolbar etc.
- @leiradel's snippets: https://github.com/leiradel/ImGuiAl/
- @nem0's snippets (in imgui_user.* files) https://github.com/nem0/LumixEngine/tree/master/external/imgui
- @aoterodelaroza's snippets [[github](https://github.com/aoterodelaroza/imgui-goodies)]
- MetricsGui: controls for displaying performance metrics [[github](https://github.com/GameTechDev/MetricsGui)]
- ImGuiVR: Demo code for using Imgui with OpenVR [[github](https://github.com/temcgraw/ImguiVR)] [[video](https://www.youtube.com/watch?v=nlwfn4HJw5E)]

### Software Renderer/Rasterizer

- Software Renderer for Dear ImGui [[github](https://github.com/emilk/imgui_software_renderer)] by @emilk
- Fast(er) Software Rasterizer for Dear ImGui [[github](https://github.com/malamanteau/ImFastRast)] by @malamanteau
- ImSoft (softraster for ImGui) [[github](https://github.com/LAK132/ImSoft)] by @LAK132

### Docking extensions

- **Official Docking Branch (October 2018): see [#2109](https://github.com/ocornut/imgui/issues/2109).**
- [old] old docking thread [#351](https://github.com/ocornut/imgui/issues/351)
- [old] @nem0's one (old LumixEngine docking), [github](https://github.com/nem0/LumixEngine/tree/v0.34/external/imgui)
- [old] @paniq's one (based on @nem0's), [github](https://github.com/ocornut/imgui/issues/351#issuecomment-219775521)
- [old] @BentleyBlanks's one (based on @paniq's), [github](https://github.com/BentleyBlanks/imguiDock)
- [old] @thennequin's ImWindow, with OS window managing, [github](https://github.com/thennequin/ImWindow)
- [old] imgui_wm: based on ImWindow, [github](https://github.com/bkaradzic/bgfx/tree/master/3rdparty/ocornut-imgui)
- [old] @edin-purkovic's one, [github](https://github.com/edin-purkovic/ImGuiDock)
- [old] @flix01's one, [github](https://github.com/Flix01/imgui/tree/2015-10-Addons/addons/imguidock)
- [old] @aoterodelaroza's one, [github](https://github.com/aoterodelaroza/imgui-goodies)

### Remoting

- RemoteImGui: send vertices over the network https://github.com/JordiRos/remoteimgui
- imgui-ws: ImGui over WebSockets https://github.com/ggerganov/imgui-ws
- Android GLES3 stub with RemoteImGui: https://github.com/CedricGuillemet/AndroidAppViewer

### Terminal / Text mode
- ImTui: Immediate Mode Text-based User Interface https://github.com/ggerganov/imtui
- tear imgui: Experiment for a terminal-based renderer for imgui https://github.com/jonvaldes/tear_imgui

### Other

- imgui_freetype renderer: [imgui/misc/freetype/](https://github.com/ocornut/imgui/tree/master/misc/freetype) (in main repo)
- ImDuino (ESP32+TFT+ImSoft+ImGui example): https://github.com/LAK132/ImDuino
- Input / IO queue for very low framerate applications: https://gist.github.com/ocornut/8417344f3506790304742b07887adf9f
- [[Screenshot Tool|screenshot_tool]]

### Building / Packaging Cruft

- Cmake https://github.com/ocornut/imgui/pull/1713 (unmerged PR, please send feedback)
- Premake5 https://github.com/ocornut/imgui/tree/features/premake5 (unmerged branch)
- Conan https://github.com/bincrafters/conan-imgui, https://bintray.com/bincrafters/public-conan/imgui%3Abincrafters
- Fips (fips-imgui): fipsified imgui for fips build system https://github.com/fungos/fips-imgui
- GN (Chromium, ninja) BUILD.gn file: https://github.com/ndsol/VolcanoSamples/blob/master/src/BUILD.gn

### Example Apps, Framework
(Please also check our [examples/](https://github.com/ocornut/imgui/tree/master/examples) folder in the repo)

- Starter project for portable app with optional GUI (GLFW/ImGui) https://github.com/abdes/asap
- Starter dear-imgui GLFW/OpenGL 3 based CMake C++ project: https://github.com/urddru/imgui-glfw
- Bimpy: bundled imgui for python: https://github.com/podgorskiy/bimpy
- imgui_dojo: an easy setup example for imgui https://github.com/LiuZHolmes/imgui_dojo

### Rust

- imgui-inspect: An inspector UI using imgui in Rust https://github.com/aclysma/imgui-inspect

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
- nuklear (A single-header ANSI C gui library) https://github.com/vurtun/nuklear
- im3d (Immediate mode rendering and 3d gizmos) https://github.com/john-chapman/im3d/projects
- small libraries with minimal dependencies https://github.com/nothings/single_file_libs

## Articles, Videos, Blog Posts

### About the IMGUI paradigm

The Immediate Mode GUI paradigm may at first appear unusual to some users. This is mainly because "Retained Mode" GUIs have been so widespread and predominant. The following links can give you a better understanding about how Immediate Mode GUIs works.
- [Johannes 'johno' Norneby's article](http://www.johno.se/book/imgui.html).
- [A presentation by Rickard Gustafsson and Johannes Algelind](http://www.cse.chalmers.se/edu/year/2011/course/TDA361/Advanced%20Computer%20Graphics/IMGUI.pdf).
- [Jari Komppa's tutorial on building an IMGUI library](http://iki.fi/sol/imgui/).
- [Casey Muratori's original video that popularized the concept](https://mollyrocket.com/861), 2005.
- [Nicolas Guillemot's CppCon'16 flash-talk about Dear ImGui](https://www.youtube.com/watch?v=LSRJ1jZq90k), 2016.
- [Thierry Excoffier's ZMV (Zero Memory Widget)](http://perso.univ-lyon1.fr/thierry.excoffier/ZMW/), 2004.

### About Dear ImGui (English)

- CppCon 2016: Nicolas Guillemot “Dear imgui," https://www.youtube.com/watch?v=LSRJ1jZq90k
- Why I think Immediate Mode GUI is way to go for GameDev tools https://gist.github.com/bkaradzic/853fd21a15542e0ec96f7268150f1b62
- An introduction to the Dear ImGui library https://blog.conan.io/2019/06/26/An-introduction-to-the-Dear-ImGui-library.html
- Integrating Dear ImGui in a custom Vulkan renderer, https://frguthmann.github.io/posts/vulkan_imgui/
- TheChernoProject: [ImGui in OpenGL](https://www.youtube.com/watch?v=nVaQuNXueFw) / [ImGui Game Engine series](https://www.youtube.com/watch?v=nVaQuNXueFw) / [ImGui Events](https://www.youtube.com/watch?v=yBP1gSbQPPM) / [Docking & Viewport](https://www.youtube.com/watch?v=lZuje-3iyVE)
- C++ DirectX 11 Engine Tutorial 35/36: Set up ImGui: [Part 35](https://www.youtube.com/watch?v=Btx_tujnyB4), [Part 36](https://www.youtube.com/watch?v=o5sJClp0HDY)
- Mana Engine: Thread safety of APIs https://medium.com/@tloch14/mana-engine-thread-safety-of-apis-7e73d482a5c6
- Using imgui with STL types (std::vector) https://eliasdaler.github.io/using-imgui-with-sfml-pt2/#using-imgui-with-stl - Note that `BeginCombo()` api since 1.53 makes it more natural to use all sorts of containers, and since 1.63 you can use InputText() will resizing callbacks (see [imgui_stl.h #2035](https://github.com/ocornut/imgui/issues/2035) for an example with std::string)
- Rust: Making a basic game ui with imgui and ggez http://iolivia.me/posts/imgui-ggez/
- Frictionless Debug UI In C++: [pdf](http://evanachahn.com/Frictionless%20Debug%20UI%20In%20C++.pdf)

### About Dear ImGui (Other languages)

- (Korean) GLFW 사용 방법 정리 (Windows 10, VS2017) https://3dshovel.blogspot.fr/2018/01/glfw-windows-10-visual-studio-2017.html
- (Japanese) Dear ImGuiの使い方まとめ https://qiita.com/mizuma/items/73218dab2f6b022b0227
- (Japanese) OpenGLやDirectXなGUIにimguiが最強すぎる https://qiita.com/Ushio/items/446d78c881334919e156
- (Japanese) 最強すぎるGUIことImGuiの見た目もイイ感じにする https://qiita.com/izumin5210/items/26eaed69eea2c4318fcd
- (Japanese) ImGuiでデバッグツール http://hikita12312.hatenablog.com/entry/2018/03/17/100535
- (Japanese) imgui で GUI を作るときのメモ https://qiita.com/syoyo/items/85571b0697f1a9cbea71
- (Japanese) OpenSiv3DでImGuiを使う https://qiita.com/RareAmayuki/items/ca802071b452b42ad630
- (Japanese) ダッシュボードオーバーレイ（OpenVR overlay）を作りimguiとDirectXで描いてみる https://qiita.com/ondorela/items/bf4bebf747f90ebf52d8
- (Polish) Szkolenie 30.01.2018 z biblioteki dear imgui [Video Part 1](https://www.youtube.com/watch?v=TOop9EGngKY) [2](https://www.youtube.com/watch?v=fh6uOdherYw) [3](https://www.youtube.com/watch?v=bF2eOvsX7kY) [4](https://www.youtube.com/watch?v=rcCReEX6h-M) [5](https://www.youtube.com/watch?v=N2Jan6IizbA) [6](https://www.youtube.com/watch?v=70A0YH9h3Ek) [7](https://www.youtube.com/watch?v=0JRaThBx9Ww) [8](https://www.youtube.com/watch?v=O7PVZ6OKDtI) [9](https://www.youtube.com/watch?v=uIp7tLqFzKo), [Slide](https://docs.google.com/presentation/d/1F3jkWkRGCNrCAKi34KXvrkZ9luhS_7RUwHwdYDTFEiY/preview#slide=id.p) 
