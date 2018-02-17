Welcome to the imgui wiki!
This wiki is in construction, doesn't have much contents and is a total mess. Enjoy :)

- [[Links, Language bindings, Engine bindings|Links]]
- [[Known Software using dear imgui|Software-using-dear-imgui]]
- [[Future features / Roadmap|Future-Features]]
- [[Developer tips|Developer-Tips]] (for people working _on_ dear imgui)
- [[A few random tips|Tips]]

imgui_club (officially maintained bits)
https://github.com/ocornut/imgui_club

- Memory Editor: [imgui_club/imgui_memory_editor/](https://github.com/ocornut/imgui_club/tree/master/imgui_memory_editor)
- Freetype font atlas renderer: [imgui_club/imgui_freetype/](https://github.com/ocornut/imgui_club/tree/master/imgui_freetype)

Third party repos

- @flix01's snippets: https://github.com/Flix01/imgui/tree/2015-10-Addons/addons in particular see his [wiki](https://github.com/Flix01/imgui/wiki/ImGui-Addons-Branch-Home)
- @leiradel's snippets: https://github.com/leiradel/ImGuiAl/
- @nem0's snippets (in imgui_user.* files) https://github.com/nem0/LumixEngine/tree/master/external/imgui
- @aoterodelaroza's snippets [[github](https://github.com/aoterodelaroza/imgui-goodies)]
- ImGuizmo (3d translation/rotation Gizmo) and ImSequencer (animation sequencer) [[github](https://github.com/CedricGuillemet/ImGuizmo)]
- ImGuiColorTextEdit: Colorizing text editor for ImGui [[github](https://github.com/BalazsJako/ImGuiColorTextEdit)]
- Zep: An embeddable editor, with optional support for using vim keystrokes. [[github](https://github.com/cmaughan/zep)]
- ImGui::Auto() leverage C++17 to automatically serialize any data into imgui interfaces [[github](https://github.com/Csabix/imgui/tree/master/auto)]
- MetricsGui: controls for displaying performance metrics [[github](https://github.com/GameTechDev/MetricsGui)]
- ImGuiVR: Demo code for using Imgui with OpenVR [[github](https://github.com/temcgraw/ImguiVR)] [[video](https://www.youtube.com/watch?v=nlwfn4HJw5E)]

Docking extensions
(Note: an official docking extension is now in the work, Dec 2017, see  [#351](https://github.com/ocornut/imgui/issues/351) and [#1542](https://github.com/ocornut/imgui/issues/1542))
- Main Docking Thread [#351](https://github.com/ocornut/imgui/issues/351)
- @nem0's one, from LumixEngine https://github.com/nem0/LumixEngine/tree/master/external/imgui
- @paniq's one (based on @nem0's), https://github.com/ocornut/imgui/issues/351#issuecomment-219775521
- @BentleyBlanks's one (based on @paniq's), https://github.com/BentleyBlanks/imguiDock
- @thennequin's one, with OS window managing https://github.com/thennequin/ImWindow
- @edin-purkovic's one https://github.com/edin-purkovic/ImGuiDock
- @flix01's one, https://github.com/Flix01/imgui/tree/2015-10-Addons/addons/imguidock
- @aoterodelaroza's one, https://github.com/aoterodelaroza/imgui-goodies

Using dear imgui with STL types (std::vector etc.)

- https://eliasdaler.github.io/using-imgui-with-sfml-pt2/#using-imgui-with-stl
- Note that `BeginCombo()` api since 1.53 makes it more natural to use all sorts of containers.

Ideas and codes

- Tabs https://github.com/ocornut/imgui/issues/261
- Splitters https://github.com/ocornut/imgui/issues/319
- Bezier widget (@r-lyeh) https://github.com/ocornut/imgui/issues/786
- Node graph editors https://github.com/ocornut/imgui/issues/306
- Log Window https://github.com/ocornut/imgui/issues/300
- IP Entry Box (@adam4813) https://github.com/ocornut/imgui/issues/388
- Pie menu test https://github.com/ocornut/imgui/issues/434
- Gamepad/keyboard navigation branch: https://github.com/ocornut/imgui/tree/navigation
- Knobs https://github.com/ocornut/imgui/issues/942#issuecomment-268369298
- Toggle Button https://github.com/ocornut/imgui/issues/1537
- Color Picker https://github.com/ocornut/imgui/issues/346 (now merged into master)
- [[Plot var helper|plot_var_example]]
- [[Screenshot Tool|screenshot_tool]]
- Gradient color generator (@galloman) https://gist.github.com/Galloman/8a5d179e432e062550972afcd1ecf112
- tear imgui: Experiment for a terminal-based renderer for imgui https://github.com/jonvaldes/tear_imgui

Articles, Talks
- CppCon 2016: Nicolas Guillemot “Dear imgui," https://www.youtube.com/watch?v=LSRJ1jZq90k
- Why I think Immediate Mode GUI is way to go for GameDev tools https://gist.github.com/bkaradzic/853fd21a15542e0ec96f7268150f1b62
- (Polish) Szkolenie 30.01.2018 z biblioteki dear imgui [Video Part 1](https://www.youtube.com/watch?v=TOop9EGngKY) [2](https://www.youtube.com/watch?v=fh6uOdherYw), [3](https://www.youtube.com/watch?v=bF2eOvsX7kY) [4](https://www.youtube.com/watch?v=rcCReEX6h-M) [5](https://www.youtube.com/watch?v=N2Jan6IizbA) [6](https://www.youtube.com/watch?v=70A0YH9h3Ek) [7](https://www.youtube.com/watch?v=0JRaThBx9Ww) [8](https://www.youtube.com/watch?v=O7PVZ6OKDtI) [9](https://www.youtube.com/watch?v=uIp7tLqFzKo), [Slide](https://docs.google.com/presentation/d/1F3jkWkRGCNrCAKi34KXvrkZ9luhS_7RUwHwdYDTFEiY/preview#slide=id.p) 
- (Japanese) OpenGLやDirectXなGUIにimguiが最強すぎる https://qiita.com/Ushio/items/446d78c881334919e156
- (Japanese) 最強すぎるGUIことImGuiの見た目もイイ感じにする https://qiita.com/izumin5210/items/26eaed69eea2c4318fcd
- (Korean) GLFW 사용 방법 정리 (Windows 10, Visual Studio 2017) https://3dshovel.blogspot.fr/2018/01/glfw-windows-10-visual-studio-2017.html

