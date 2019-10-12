## About the IMGUI paradigm

The Immediate Mode GUI paradigm may at first appear unusual to some users. This is mainly because "Retained Mode" GUIs have been so widespread and predominant. The following links can give you a better understanding about how Immediate Mode GUIs works.
- [Johannes 'johno' Norneby's article](http://www.johno.se/book/imgui.html).
- [A presentation by Rickard Gustafsson and Johannes Algelind](http://www.cse.chalmers.se/edu/year/2011/course/TDA361/Advanced%20Computer%20Graphics/IMGUI.pdf).
- [Jari Komppa's tutorial on building an IMGUI library](http://iki.fi/sol/imgui/).
- [Casey Muratori's original video that popularized the concept](https://mollyrocket.com/861), 2005.
- [Nicolas Guillemot's CppCon'16 flash-talk about Dear ImGui](https://www.youtube.com/watch?v=LSRJ1jZq90k), 2016.
- [Thierry Excoffier's ZMV (Zero Memory Widget)](http://perso.univ-lyon1.fr/thierry.excoffier/ZMW/), 2004.

## About Dear ImGui

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
- (Polish) Szkolenie 30.01.2018 z biblioteki dear imgui [Video Part 1](https://www.youtube.com/watch?v=TOop9EGngKY) [2](https://www.youtube.com/watch?v=fh6uOdherYw) [3](https://www.youtube.com/watch?v=bF2eOvsX7kY) [4](https://www.youtube.com/watch?v=rcCReEX6h-M) [5](https://www.youtube.com/watch?v=N2Jan6IizbA) [6](https://www.youtube.com/watch?v=70A0YH9h3Ek) [7](https://www.youtube.com/watch?v=0JRaThBx9Ww) [8](https://www.youtube.com/watch?v=O7PVZ6OKDtI) [9](https://www.youtube.com/watch?v=uIp7tLqFzKo), [Slide](https://docs.google.com/presentation/d/1F3jkWkRGCNrCAKi34KXvrkZ9luhS_7RUwHwdYDTFEiY/preview#slide=id.p) 
- (Japanese) OpenGLやDirectXなGUIにimguiが最強すぎる https://qiita.com/Ushio/items/446d78c881334919e156
- (Japanese) 最強すぎるGUIことImGuiの見た目もイイ感じにする https://qiita.com/izumin5210/items/26eaed69eea2c4318fcd
- (Japanese) ImGuiでデバッグツール http://hikita12312.hatenablog.com/entry/2018/03/17/100535
- (Japanese) imgui で GUI を作るときのメモ https://qiita.com/syoyo/items/85571b0697f1a9cbea71
- (Japanese) OpenSiv3DでImGuiを使う https://qiita.com/RareAmayuki/items/ca802071b452b42ad630
- (Japanese) ダッシュボードオーバーレイ（OpenVR overlay）を作りimguiとDirectXで描いてみる https://qiita.com/ondorela/items/bf4bebf747f90ebf52d8
- (Korean) GLFW 사용 방법 정리 (Windows 10, VS2017) https://3dshovel.blogspot.fr/2018/01/glfw-windows-10-visual-studio-2017.html
