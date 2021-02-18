## Community

If you are experienced with Dear ImGui, please consider helping people and answering questions on Issues and Discord!

- [Github Issues](https://github.com/ocornut/imgui/issues/): for feature requests, bug reports, feedback, code snippets, etc. 
- [Discord Chat](https://discordapp.com/channels/613733622192668672/613733622721019908) / [Invite](https://discord.gg/NgJ4SEP): general chat room. if you have issues compiling, linking, running or displaying Dear ImGui (render or inputs, portability issues, using the examples, adding fonts).
- Prefer using GitHub Issues: questions and answers will be available to others and you can search for old questions. It is more likely you will receive a correct and detailed answer on GitHub. 
- [#2261](https://github.com/ocornut/imgui/issues/2261) How to open an Issue or Pull Request
- [[Help wanted|Help-wanted]]

## General documentation

- **[[FAQ (Frequently Asked Questions)|https://github.com/ocornut/imgui/blob/master/docs/FAQ.md]]** (docs/FAQ.md)
- [Homepage](https://github.com/ocornut/imgui/blob/master/docs/README.md) (docs/README.md)
- [[Glossary|Glossary]]
- [[Software using Dear ImGui|Software-using-dear-imgui]]
- [[User quotes|Quotes]]
- [[Incoming work|Incoming-work]]
- [[Tips|Tips]] (for people working _with_ dear imgui)
- [[Developer tips|Developer-Tips]] (for people working _on_ dear imgui)
- [Releases / Changelogs](https://github.com/ocornut/imgui/releases) with annotation and pictures.

## Gallery

- [#3793](https://github.com/ocornut/imgui/issues/3793) Gallery: Post your screenshots / code here
- [[Useful widgets gallery|Useful-widgets]]

## Branches

- master
- docking

## Demo, Examples

- The [examples/](https://github.com/ocornut/imgui/tree/master/examples) folder contains 21 standalone example application for varieties of platforms and frameworks.
- Read: [About Examples apps](https://github.com/ocornut/imgui/blob/master/docs/EXAMPLES.md) (docs/EXAMPLES.md)
- The [imgui_demo.cpp](https://github.com/ocornut/imgui/tree/master/imgui_demo.cpp) file has a `ImGui::ShowDemoWindow()` function which you can call from any imgui-enabled application to showcase variety of features. The demo function is called from all examples/ apps.
- Third-party: @pthom's [imgui_manual](https://pthom.github.io/imgui_manual_online/manual/imgui_manual.html): web version of imgui_demo with interactive browsing of sources.

## Backends, Bindings

- The [backends/](https://github.com/ocornut/imgui/tree/master/backends) folder contains 16 reusable backends for varieties of platforms and frameworks.
- Read: [About Backends](https://github.com/ocornut/imgui/blob/master/docs/BACKENDS.md) (docs/BACKENDS.md)
- [List of language bindings](https://github.com/ocornut/imgui/wiki/Bindings#language-bindings) (C, C#, D, Go,  JavaScript, Lua, Rust and many others)
- [List of engine/framework backends](https://github.com/ocornut/imgui/wiki/Bindings#frameworkengine-bindingsbackends)

## Third-party extensions

- [[List of useful third-party widgets and extensions|Useful-widgets]]**

## Images

- Tutorial: [[Image Loading and Displaying Examples|Image-Loading-and-Displaying-Examples]]

## Fonts/Text

- Read: [Using Fonts](https://github.com/ocornut/imgui/blob/master/docs/FONTS.md) (docs/FONTS.md)
- Search in Issues: [font/text](https://github.com/ocornut/imgui/issues?q=label%3Afont%2Ftext+)
- Freetype renderer: [imgui_freetype](https://github.com/ocornut/imgui/tree/master/misc/freetype) (misc/freetype)

## Tables

- [#3740](https://github.com/ocornut/imgui/issues/3740) Tables Topic (1.80+)
- Search in Issues: [tables/columns](https://github.com/ocornut/imgui/issues?q=label%3Atables%2Fcolumns+)

## Docking

- Read: [[About Docking|Docking]]
- Search in Issues: [docking](https://github.com/ocornut/imgui/issues?q=label%3Adocking+)
- [#2109](https://github.com/ocornut/imgui/issues/2109) Docking Topic (`docking` branch)
- [List of legacy third-party Docking extensions](https://github.com/ocornut/imgui/wiki/Docking#legacy-third-party-docking-extensions) (prior to official docking: LumixEngine, imguiDock, ImWindow, imgui_wm, etc.)

## Multi-viewports

- Read: [[Multi-Viewports|Multi-Viewports]]
- Search in Issues: [multi-viewports](https://github.com/ocornut/imgui/issues?q=label%3Amulti-viewports+)
- [#1542](https://github.com/ocornut/imgui/issues/1542) Main multi-viewports topic
- [#2117](https://github.com/ocornut/imgui/issues/2117) Linux/Mac compatibility of multi-viewports

## Building

- [#1713](https://github.com/ocornut/imgui/pull/1713) CMake project to build Examples (PR) by @podsvirov (unmerged, please send feedback)
- [#3027](https://github.com/ocornut/imgui/pull/3027) Add CMake configuration (PR) by @Qix- (unmerged, please send feedback)
- [rokups' cmake](https://github.com/rokups/imgui/blob/rk/cmake/CMakeLists.txt) Self-contained single-file cmake build script
- Premake5 https://github.com/ocornut/imgui/tree/features/premake5 (unmerged branch)
- Conan https://github.com/bincrafters/conan-imgui, https://bintray.com/bincrafters/public-conan/imgui%3Abincrafters
- Fips (fips-imgui): fipsified imgui for fips build system https://github.com/fungos/fips-imgui
- GN (Chromium, ninja) BUILD.gn file: https://github.com/ndsol/VolcanoSamples/blob/master/src/BUILD.gn

## Inputs

- Input / IO queue for very low framerate applications: [gist](https://gist.github.com/ocornut/8417344f3506790304742b07887adf9f)

## Third-party Frameworks

- asap: Starter project for portable app with optional GUI (GLFW/ImGui) https://github.com/abdes/asap
- imgui-app: amalgamation of Dear ImGui and Sokol into two files https://github.com/pplux/imgui-app/
- Bimpy: bundled imgui for python: https://github.com/podgorskiy/bimpy
- giu: Cross platform rapid GUI framework for golang based on Dear ImGui. https://github.com/AllenDang/giu
- Dear PyGui: A Simple Python GUI framework https://github.com/hoffstadt/DearPyGui
- imgui_dojo: an easy setup example for imgui https://github.com/LiuZHolmes/imgui_dojo
- mahi-gui: Dirt Simple C++ GUI Toolkit using GLFW, glad, and ImGui https://github.com/mahilab/mahi-gui
- sdl-bgfx-imgui-starter: A starter project for graphics applications https://github.com/pr0g/sdl-bgfx-imgui-starter
- Starter dear-imgui GLFW/OpenGL 3 based CMake C++ project: https://github.com/urddru/imgui-glfw
- ImDuino (ESP32+TFT+ImSoft+ImGui example): https://github.com/LAK132/ImDuino
