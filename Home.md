Welcome to the Dear ImGui wiki!
This wiki is in construction.
Feel free to edit and contribute!

## Forums

- [Discourse Forum](https://discourse.dearimgui.org/) - if you have issues compiling, linking, running or displaying Dear ImGui (render or inputs, portability issues, using the examples, adding fonts). If you are experienced with Dear ImGui, please consider helping people and answering questions there!
- [Github issues](https://github.com/ocornut/imgui/issues/) - for feature requests, bug reports, feedback, code snippets, etc. If you are experienced with Dear ImGui, please consider helping people and answering questions there!

## Wiki Pages

- [[Language bindings, Framework/Engine bindings|Bindings]]
- [[Software using dear imgui|Software-using-dear-imgui]]
- [[User quotes|Quotes]]
- [[Help wanted|Help-wanted]]
- [[Incoming work|Incoming-work]]
- [[Developer tips|Developer-Tips]] (for people working _on_ dear imgui)
- [[Tips|Tips]] (for people working _with_ dear imgui)
- [[Loading Font Example|Loading-Font-Example]] (w/ Japanese font)

## Issues: Some Important Topics

- [#2109](https://github.com/ocornut/imgui/issues/2109) Docking branch available for testing
- [#1542](https://github.com/ocornut/imgui/issues/1542) Multi-viewports / virtual viewports Branch
- [#2117](https://github.com/ocornut/imgui/issues/2117) Linux/Mac compatibility of the multi-viewport branch
- [#2265](https://github.com/ocornut/imgui/issues/2265) Gallery
- [#1713](https://github.com/ocornut/imgui/pull/1713) CMake project (PR) by @podsvirov

## Issues: Labels

- https://github.com/ocornut/imgui/labels

## Articles, Video, Talks

- CppCon 2016: Nicolas Guillemot “Dear imgui," https://www.youtube.com/watch?v=LSRJ1jZq90k
- Why I think Immediate Mode GUI is way to go for GameDev tools https://gist.github.com/bkaradzic/853fd21a15542e0ec96f7268150f1b62
- TheChernoProject: [ImGui in OpenGL](https://www.youtube.com/watch?v=nVaQuNXueFw) / [ImGui Game Engine series](https://www.youtube.com/watch?v=nVaQuNXueFw) / [ImGui Events](https://www.youtube.com/watch?v=yBP1gSbQPPM) / [Docking & Viewport](https://www.youtube.com/watch?v=lZuje-3iyVE)
- C++ DirectX 11 Engine Tutorial 35/36: Set up ImGui: [Part 35](https://www.youtube.com/watch?v=Btx_tujnyB4), [Part 36](https://www.youtube.com/watch?v=o5sJClp0HDY)
- Mana Engine: Thread safety of APIs https://medium.com/@tloch14/mana-engine-thread-safety-of-apis-7e73d482a5c6
- Using imgui with STL types (std::vector) https://eliasdaler.github.io/using-imgui-with-sfml-pt2/#using-imgui-with-stl - Note that `BeginCombo()` api since 1.53 makes it more natural to use all sorts of containers, and since 1.63 you can use InputText() will resizing callbacks (see [imgui_stl.h #2035](https://github.com/ocornut/imgui/issues/2035) for an example with std::string)
- Rust: Making a basic game ui with imgui and ggez http://iolivia.me/posts/imgui-ggez/
- (Polish) Szkolenie 30.01.2018 z biblioteki dear imgui [Video Part 1](https://www.youtube.com/watch?v=TOop9EGngKY) [2](https://www.youtube.com/watch?v=fh6uOdherYw) [3](https://www.youtube.com/watch?v=bF2eOvsX7kY) [4](https://www.youtube.com/watch?v=rcCReEX6h-M) [5](https://www.youtube.com/watch?v=N2Jan6IizbA) [6](https://www.youtube.com/watch?v=70A0YH9h3Ek) [7](https://www.youtube.com/watch?v=0JRaThBx9Ww) [8](https://www.youtube.com/watch?v=O7PVZ6OKDtI) [9](https://www.youtube.com/watch?v=uIp7tLqFzKo), [Slide](https://docs.google.com/presentation/d/1F3jkWkRGCNrCAKi34KXvrkZ9luhS_7RUwHwdYDTFEiY/preview#slide=id.p) 
- (Japanese) OpenGLやDirectXなGUIにimguiが最強すぎる https://qiita.com/Ushio/items/446d78c881334919e156
- (Japanese) 最強すぎるGUIことImGuiの見た目もイイ感じにする https://qiita.com/izumin5210/items/26eaed69eea2c4318fcd
- (Japanese) ImGuiでデバッグツール http://hikita12312.hatenablog.com/entry/2018/03/17/100535
- (Japanese) OpenSiv3DでImGuiを使う https://qiita.com/RareAmayuki/items/ca802071b452b42ad630
- (Japanese) ダッシュボードオーバーレイ（OpenVR overlay）を作りimguiとDirectXで描いてみる https://qiita.com/ondorela/items/bf4bebf747f90ebf52d8
- (Korean) GLFW 사용 방법 정리 (Windows 10, VS2017) https://3dshovel.blogspot.fr/2018/01/glfw-windows-10-visual-studio-2017.html

## Code

### imgui_club 
(officially maintained bits)

- Memory Editor: [imgui_club/imgui_memory_editor/](https://github.com/ocornut/imgui_club/tree/master/imgui_memory_editor)
- Freetype renderer: [imgui/misc/freetype/](https://github.com/ocornut/imgui/tree/master/misc/freetype)

### Third party repos

- @flix01's addons: [ImGui-Addons-Branch-Home](https://github.com/Flix01/imgui/wiki/ImGui-Addons-Branch-Home) for instructions and [github repo](https://github.com/Flix01/imgui) for code.
- @leiradel's snippets: https://github.com/leiradel/ImGuiAl/
- @nem0's snippets (in imgui_user.* files) https://github.com/nem0/LumixEngine/tree/master/external/imgui
- @aoterodelaroza's snippets [[github](https://github.com/aoterodelaroza/imgui-goodies)]
- ImGuizmo (3d translation/rotation Gizmo) and ImSequencer (animation sequencer) [[github](https://github.com/CedricGuillemet/ImGuizmo)]
- ImGui::Auto() leverage C++17 to automatically serialize any data into imgui interfaces [[github](https://github.com/Csabix/imgui/tree/master/auto)]
- MetricsGui: controls for displaying performance metrics [[github](https://github.com/GameTechDev/MetricsGui)]
- ImGuiVR: Demo code for using Imgui with OpenVR [[github](https://github.com/temcgraw/ImguiVR)] [[video](https://www.youtube.com/watch?v=nlwfn4HJw5E)]
- Software Renderer for Dear ImGui [[github](https://github.com/emilk/imgui_software_renderer)] by @emilk

### Text Editors
- ImGuiColorTextEdit: Colorizing text editor for ImGui [[github](https://github.com/BalazsJako/ImGuiColorTextEdit)]
- Zep: An embeddable editor, with optional support for using vim keystrokes. [[github](https://github.com/cmaughan/zep)]
- Scintilla integration [[thread](https://github.com/ocornut/imgui/issues/108)]

### Docking extensions
- **Official Docking Branch (October 2018): see [#2109](https://github.com/ocornut/imgui/issues/2109).**
- [old] Docking Thread [#351](https://github.com/ocornut/imgui/issues/351)
- [old] @nem0's one, from LumixEngine https://github.com/nem0/LumixEngine/tree/master/external/imgui
- [old] @paniq's one (based on @nem0's), https://github.com/ocornut/imgui/issues/351#issuecomment-219775521
- [old] @BentleyBlanks's one (based on @paniq's), https://github.com/BentleyBlanks/imguiDock
- [old] @thennequin's ImWindow, with OS window managing https://github.com/thennequin/ImWindow
- [old] imgui_wm: based on ImWindow https://github.com/bkaradzic/bgfx/tree/master/3rdparty/ocornut-imgui 
- [old] @edin-purkovic's one https://github.com/edin-purkovic/ImGuiDock
- [old] @flix01's one, https://github.com/Flix01/imgui/tree/2015-10-Addons/addons/imguidock
- [old] @aoterodelaroza's one, https://github.com/aoterodelaroza/imgui-goodies

### Remoting

- RemoteImGui: send vertices over the network https://github.com/JordiRos/remoteimgui
- Android GLES3 stub with RemoteImGui: https://github.com/CedricGuillemet/AndroidAppViewer

### Other

- Input / IO queue for very low framerate applications: https://gist.github.com/ocornut/8417344f3506790304742b07887adf9f
- Markdown: https://github.com/juliettef/imgui_markdown
- Splitters: https://github.com/ocornut/imgui/issues/319
- Bezier widget (@r-lyeh) https://github.com/ocornut/imgui/issues/786
- Spinner + Loading Bar progress indicators: https://github.com/ocornut/imgui/issues/1901
- Node graph editors: https://github.com/ocornut/imgui/issues/306
- Log Window: https://github.com/ocornut/imgui/issues/300
- IP Entry Box (@adam4813) https://github.com/ocornut/imgui/issues/388
- Pie menu test: https://github.com/ocornut/imgui/issues/434
- Knobs: https://github.com/ocornut/imgui/issues/942#issuecomment-268369298
- URL/Links: https://gist.github.com/dougbinks/ef0962ef6ebe2cadae76c4e9f0586c69#file-imguiutils-h-L228-L262
- Toggle Button: https://github.com/ocornut/imgui/issues/1537
- [[Plot var helper|plot_var_example]]
- [[Screenshot Tool|screenshot_tool]]
- Gradient color generator (@galloscript): https://gist.github.com/galloscript/8a5d179e432e062550972afcd1ecf112
- tear imgui: Experiment for a terminal-based renderer for imgui https://github.com/jonvaldes/tear_imgui

### Building / Packaging Cruft

- Cmake https://github.com/ocornut/imgui/pull/1713 (unmerged PR, please send feedback)
- Conan https://github.com/bincrafters/conan-imgui, https://bintray.com/bincrafters/public-conan/imgui%3Abincrafters
- Fips (fips-imgui): fipsified imgui for fips build system https://github.com/fungos/fips-imgui

### Example Apps, Framework
(Please also check our [examples/](https://github.com/ocornut/imgui/tree/master/examples) folder in the repo)

- Starter project for portable app with optional GUI (GLFW/ImGui) https://github.com/abdes/asap
- Starter dear-imgui GLFW/OpenGL 3 based CMake C++ project: https://github.com/urddru/imgui-glfw
- Bimpy: bundled imgui for python: https://github.com/podgorskiy/bimpy

### Related/Suggested Librairies

- stb (stb single-file public domain libraries for C/C++) https://github.com/nothings/stb/
- nuklear (A single-header ANSI C gui library) https://github.com/vurtun/nuklear
- im3d (Immediate mode rendering and 3d gizmos) https://github.com/john-chapman/im3d/projects
- small libraries with minimal dependencies https://github.com/nothings/single_file_libs
