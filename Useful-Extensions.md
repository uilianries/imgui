_(wiki editors: the images on this page are 500x250 pixels. please try to keep new images the same size)_
<BR>_(help wanted: add missing 500x250 images for links that don't have one!)_ 

## Index

- [Automation / Testing](#automation--testing)
- [Text Editors](#text-editors)
- [Node Editors](#node-editors)
- [Plotting, Graph](#plotting-graph)
- [Curves, Animations, Gradients Editors](#curves-animations-gradients-editors)
- [File Browsers / File Dialog](#file-browsers--file-dialog)
- [Input Method Editors](#input-method-editors)
- [Knobs](#knobs)
- [Spinners](#spinners)
- [Toggles](#toggles)
- [Layout](#layout)
- [GUI/Layout Editor/Generator](#guilayout-editorgenerator)
- [Styling](#styling)
- [Software Renderer/Rasterizer](#software-rendererrasterizer)
- [Remoting](#remoting)
- [Terminal / Text mode](#terminal--text-mode)
- [Midi/OSC interfacing](#midiosc-interfacing)
- [Virtual Reality (VR) / Reprojected UI plane](#virtual-reality-vr--reprojected-ui-plane)
- [Image manipulation](#image-manipulation)
- [3D manipulation Gizmos](#3d-manipulation-gizmos)
- [Inspectors, Serialization](#inspectors-serialization)
- [C++ness](#cness)
- [Miscellaneous](#miscellaneous)
- [Third Party Repos](#third-party-repos)

# Automation / Testing

**imgui_test_engine**: Dear ImGui Test Engine + Test Suite
<BR> [github/ocornut/imgui_test_engine](https://github.com/ocornut/imgui_test_engine)
<BR> ![imgui_test_engine](https://user-images.githubusercontent.com/8225057/203781606-6a544fed-1696-49ab-ba2f-12786d6871b0.png)

# Text Editors

**ImGuiColorTextEdit**: Colorizing text editor for Dear ImGui (2017-2019)
<BR> [github/BalazsJako/ImGuiColorTextEdit](https://github.com/BalazsJako/ImGuiColorTextEdit)
<BR> ![](https://user-images.githubusercontent.com/8225057/103882739-89365a80-50dc-11eb-98e4-d1ccccb640bd.png)

**Zep**: An embeddable editor, with optional support for using vim keystrokes (2018-2022)
<BR> [github/Rezonality/zep](https://github.com/Rezonality/zep)
<BR> ![](https://user-images.githubusercontent.com/8225057/97189667-21db6080-17a5-11eb-9e3e-aa794fc45831.png)

**Scintilla** integration (2015)
<BR> [issue #108](https://github.com/ocornut/imgui/issues/108) (likely obsolete)
<BR> ![](https://user-images.githubusercontent.com/1193295/103753586-80298880-500b-11eb-97ca-d6674bc22d35.png)

# Node Editors

**imgui-node-editor**: node editor using Dear ImGui (2016-2021)
<BR> [github/thedmd/imgui-node-editor](https://github.com/thedmd/imgui-node-editor)
<BR> ![](https://user-images.githubusercontent.com/1193295/96736564-06dfa980-13bd-11eb-8cf8-641962bb04df.png)

**ImNodes**: Node graph implementation for Dear ImGui (2019)
<BR> [github/rokups/ImNodes](https://github.com/rokups/ImNodes)
<BR> ![](https://user-images.githubusercontent.com/1193295/96736823-49a18180-13bd-11eb-8891-95f481fe1765.png)

**imnodes**: A small, dependency-free node editor for dear imgui (2019-2020)
<BR> [github/Nelarius/imnodes](https://github.com/Nelarius/imnodes)
<BR> ![](https://user-images.githubusercontent.com/1193295/96736995-78b7f300-13bd-11eb-84a1-6b8f0e4ac064.png)

Many more Node Editors at [#306](https://github.com/ocornut/imgui/issues/306).

# Plotting, Graph

**ImPlot**: Advanced 2D Plotting for Dear ImGui (2020-2022)
<BR> [github/epezent/implot](https://github.com/epezent/implot)
<BR> ![](https://user-images.githubusercontent.com/1193295/96738879-79ea1f80-13bf-11eb-8e96-97f4acc8b79d.png)

**imgui-plot** (2019)
<BR> [github/soulthreads/imgui-plot](https://github.com/soulthreads/imgui-plot)
<BR> ![](https://user-images.githubusercontent.com/1193295/96739012-9f772900-13bf-11eb-831b-e4b1ba82e152.png)

**Flame Graph Widget** (2019)
<BR> [issue #2859](https://github.com/ocornut/imgui/issues/2859)
<BR> ![](https://user-images.githubusercontent.com/1193295/96739187-d0575e00-13bf-11eb-9afa-6f0c2bc4dd0f.png)

**Plot Var Helper** (2016)
<BR> [comment](https://github.com/ocornut/imgui/issues/1772#issuecomment-1127830067)
<BR> ![](https://user-images.githubusercontent.com/1193295/96739299-f0871d00-13bf-11eb-8a2b-fa670070477d.png)

# Curves, Animations, Gradients Editors

**Cubic Bezier / Curve Editor** (2016-2019)
<BR> [github](https://github.com/ocornut/imgui/issues/786)
<BR> ![](https://user-images.githubusercontent.com/1193295/96737312-d1878b80-13bd-11eb-92ae-62dc191c6ee1.png)

**ImSequencer**: animation sequencer (2018-2019)
<BR> [github/CedricGuillemet/ImGuizmo](https://github.com/CedricGuillemet/ImGuizmo)
<BR> ![](https://user-images.githubusercontent.com/1193295/96737563-1ad7db00-13be-11eb-974d-956ba41b11de.png)

**ImGradient**: gradient editor (2018)
<BR> [github/CedricGuillemet/ImGuizmo](https://github.com/CedricGuillemet/ImGuizmo)

**ImCurveEdit**: curve editor (2018)
<BR> [github/CedricGuillemet/ImGuizmo](https://github.com/CedricGuillemet/ImGuizmo)

**Gradient Color Generator** (2016)
<BR> [gist/galloscript](https://gist.github.com/galloscript/8a5d179e432e062550972afcd1ecf112)

**im-neo-sequencer** (2022)
<BR> [gitlab/GroGy/im-neo-sequencer](https://gitlab.com/GroGy/im-neo-sequencer) / [discussion](https://github.com/ocornut/imgui/issues/4967)
<BR> ![image](https://user-images.githubusercontent.com/8225057/230399492-3e20d754-50a1-4210-82b2-76d001c5c377.png)

# File Browsers / File Dialog

**ImFileDialog**: A simple file dialog library [... ] supports favorites, actual Windows icons, image previews, zooming in, (2021)
<BR> [github/dfranx/ImFileDialog](https://github.com/dfranx/ImFileDialog)
<BR> ![ImFileDialog](https://user-images.githubusercontent.com/8225057/107156759-88654280-6980-11eb-88ea-774b3119d4d3.png)

**imfile**: Rust-only file dialog for ImGui (2023)
<BR> [github/tseli0s/imfile](https://github.com/tseli0s/imfile)

**L2DFileDialog** (2020)
<BR> [github/Limeoats/L2DFileDialog](https://github.com/Limeoats/L2DFileDialog)
<BR> ![](https://user-images.githubusercontent.com/1193295/103759110-79067880-5013-11eb-9fc5-522f3bb9e5df.png)

**aiekick/ImGuiFileDialog** : (2019-2021) (win/linux/mac) thumbnails, advanced file styling, custom pane, bookmarks, etc..
<BR> [github/aiekick/ImGuiFileDialog](https://github.com/aiekick/ImGuiFileDialog)
<BR> ![](https://user-images.githubusercontent.com/1434736/139579841-975a72de-c70c-4132-a3e3-20dd564d858f.png)

**AirGuanZ's imgui-filebrowser**
<BR> [github/AirGuanZ-imgui-filebrowser](https://github.com/AirGuanZ/imgui-filebrowser)
<BR> ![](https://user-images.githubusercontent.com/1193295/96841762-781a6d80-144c-11eb-9ef9-7f9c3bda37d1.png)

**gallickgunner's ImGui-Addons**
<BR> [github/gallickgunner/ImGui-Addons](https://github.com/gallickgunner/ImGui-Addons)
<BR> ![](https://user-images.githubusercontent.com/1193295/103759229-afdc8e80-5013-11eb-900b-117cde27157a.png)

**Flix01's ImGui-Addons**
<BR> [github/Flix01/imgui](https://github.com/Flix01/imgui/wiki/ImGui-Addons-Branch-Home)
<BR> ![](https://user-images.githubusercontent.com/1193295/103753755-b8c96200-500b-11eb-95c0-3ff6ff19e78e.png)

# Rich text

**imgui_markdown**: Markdown for Dear ImGui (2019-2021)
<BR> [github/juliettef/imgui_markdown](https://github.com/juliettef/imgui_markdown)
<BR> ![](https://user-images.githubusercontent.com/8225057/97190844-89de7680-17a6-11eb-8add-5cab6be7f5f5.png)

**imgui_md**: Markdown renderer for Dear ImGui using MD4C parser (2021)
<BR> [github/mekhontsev/imgui_md](https://github.com/mekhontsev/imgui_md)
<BR> ![](https://user-images.githubusercontent.com/8225057/113867323-b0b9c380-97ae-11eb-9b8d-5a0583ccebed.png)

**url/links**
<BR> [gist/dougbinks](https://gist.github.com/dougbinks/ef0962ef6ebe2cadae76c4e9f0586c69#file-imguiutils-h-L228-L262)

# Input Method Editors

**DearImGui-with-IMM32**: Microsoft IME Overlay using Dear ImGui (2020)
<BR> [github/maildrop/DearImGui-with-IMM32](https://github.com/maildrop/DearImGui-with-IMM32)
<BR> ![](https://user-images.githubusercontent.com/1193295/96867731-64333380-146d-11eb-9aae-14abee458f93.png)

# Knobs

**imgui-rs-knobs**: A library for designing knobs for imgui-rs [Rust] (2021)
<BR> [github/DGriffin91/imgui-rs-knobs](https://github.com/DGriffin91/imgui-rs-knobs)
<BR> ![](https://user-images.githubusercontent.com/8225057/165107365-b1ee845e-a858-405d-85e9-f892a7f4545e.png)

**imgui-knobs**: This is a port/adaptation of imgui-rs-knobs (2022)
<BR> ![image](https://user-images.githubusercontent.com/8225057/165107682-88d91eec-387b-493c-859b-17fcfa5b14ba.png)
<BR> [github/altschuler/imgui-knobs](https://github.com/altschuler/imgui-knobs)

**thread**
<BR> [issue #942](https://github.com/ocornut/imgui/issues/942#issuecomment-268369298)
<BR> ![](https://user-images.githubusercontent.com/1193295/96877128-8cc12a80-1479-11eb-9d19-904ceaf8e469.png)

# Spinners

**imspinner**: Set of nice spinners for imgui (2022)
<BR> [github/dalerank/imspinner](https://github.com/dalerank/imspinner) / [issue #5421](https://github.com/ocornut/imgui/issues/5421)
<BR> ![](https://user-images.githubusercontent.com/8225057/176230882-2261909d-63a6-446d-9c2d-78023e932aa2.png)

**Spinner/Loading progress indicators**
<BR> [issue #1901](https://github.com/ocornut/imgui/issues/1901)

# Toggles

**Toggle Button**
<BR> [issue #1537](https://github.com/ocornut/imgui/issues/1537)
<BR> ![](https://user-images.githubusercontent.com/1193295/96878596-51bff680-147b-11eb-8ded-f0bc241fa984.png)

**imgui_toggle** (2022)
<BR> [github/cmdwft/imgui_toggle](https://github.com/cmdwtf/imgui_toggle)

# Layout

**Stack Layout implementation**
<BR> https://github.com/ocornut/imgui/pull/846

# GUI/Layout Editor/Generator

**ImRAD** (2023)
<BR> [github/tpecholt/imrad](https://github.com/tpecholt/imrad)
<BR> ![](https://user-images.githubusercontent.com/8225057/230587989-6416cb83-743f-4267-91c8-4ef9b1032adc.png)

**ImStudio** (2021-2022)
<BR> [github/Raais/ImStudio](https://github.com/Raais/ImStudio), [web app](https://raais.github.io/ImStudio/)
<BR>![](https://user-images.githubusercontent.com/8225057/230587695-ed9d5e0c-8085-4a00-96f5-acc0f4e49742.png)

**ImGuiBuilder**: gui editor of the Imgui framework (2021)
<BR> [github/Code-Building/ImGuiBuilder](https://github.com/Code-Building/ImGuiBuilder)
<BR> ![](https://user-images.githubusercontent.com/8225057/230587226-126135d2-54b0-48bd-8b14-719af5786010.png)

**ImGuiDesigner**: interactive gui editor (2023)
<BR> [github/iamclint/ImGuiDesigner](https://github.com/iamclint/ImGuiDesigner)
<BR>![designer](https://github.com/ocornut/imgui/assets/16273696/49cdee7d-d5df-4fe6-89b2-ed7531e5c74a)

# Styling

**Thread: Using gradients in widgets** (2021)
<BR> https://github.com/ocornut/imgui/issues/4722
<BR> ![](https://user-images.githubusercontent.com/8225057/147111952-c821a269-5d3e-44b0-9bfa-73a12ee7539b.png)

**imgui-spectrum** ImGui library [...] embracing Adobe's Spectrum guidelines
<BR> https://github.com/adobe/imgui/blob/master/docs/Spectrum.md
<BR> ![](https://user-images.githubusercontent.com/8225057/165113374-8f5d815d-54d0-47ed-bbc5-afa1eb026af5.png)

# Software Renderer/Rasterizer

**Software Renderer for Dear ImGui** (2018)
<BR> [github/emilk/imgui_software_renderer](https://github.com/emilk/imgui_software_renderer)
<BR> ![](https://user-images.githubusercontent.com/1193295/96886295-bc753000-1483-11eb-863e-81056c1bd801.png)

**ImSoft (softraster for ImGui)** (2019)
<BR> [github/LAK132/ImSoft](https://github.com/LAK132/ImSoft/blob/master/examples/imgui_impl_softraster.cpp)

**Fast(er) Software Rasterizer for Dear ImGui**
<BR> [github/malamanteau](https://github.com/malamanteau/ImFastRast) [down]

# Remoting

**netImGui: Dear ImGui remote access library and application** (2020-2022)
<BR> [github/sammyfreg/netImgui](https://github.com/sammyfreg/netImgui)
<BR>+ **UnrealNetImgui**: Unreal Engine 4's support of NetImgui. (2020-2022)
<BR> [https://github.com/sammyfreg/UnrealNetImgui](https://github.com/sammyfreg/UnrealNetImgui)
<BR> ![](https://user-images.githubusercontent.com/1193295/103900082-acbace80-50f7-11eb-824e-c28623b1d6c3.png)

**imgui-ws**: Dear ImGui over WebSockets (2019-2022)
<BR> [github/ggerganov/imgui-ws](https://github.com/ggerganov/imgui-ws)
<BR> ![](https://user-images.githubusercontent.com/1193295/103754230-62105800-500c-11eb-9540-8dc7b6ad59c9.png)

**RemoteImGui**: send vertices over the network (2014-2022)
<BR> [github/JordiRos/remoteimgui](https://github.com/JordiRos/remoteimgui)

**AndroidAppViewer**: Android GLES3 stub with RemoteImGui (2018-2019)
<BR> [github/CedricGuillemet/AndroidAppViewer](https://github.com/CedricGuillemet/AndroidAppViewer)
<BR> ![](https://user-images.githubusercontent.com/1193295/96888707-31e20000-1486-11eb-8c2d-05bfe12998a1.png)

# Terminal / Text mode

**ImTui**: Immediate Mode Text-based User Interface (2019-2021)
<BR> [github/ggerganov/imtui](https://github.com/ggerganov/imtui)
<BR> ![](https://user-images.githubusercontent.com/1193295/103759425-ffbb5580-5013-11eb-8bca-203679ac3a45.png)

**tear imgui**: Experiment for a terminal-based renderer for imgui (2017)
<BR> [github/jonvaldes/tear_imgui](https://github.com/jonvaldes/tear_imgui)

# Midi/OSC interfacing

**midi2osc**: midi to opensoundcontrol bridge (2018-2020)
<BR> [github/mmalex/midi2osc](https://github.com/mmalex/midi2osc)
<BR> ![](https://user-images.githubusercontent.com/1193295/96889160-9ef59580-1486-11eb-9938-ae98c52dd4f3.png)

**devmidi**: A simple MIDI input library that also dovetails into Dear ImGui (2020)
<BR> [github/antonthefirst/devmidi](https://github.com/antonthefirst/devmidi)

**shric/midi**: A C++ program to read midi input and display things with Dear ImGui (2020)
<BR> [github/shric/midi](https://github.com/shric/midi)
<BR> ![shric/midi](https://user-images.githubusercontent.com/8225057/107155358-3cae9b00-6978-11eb-981a-2d4bd935bf4b.png)

# Virtual Reality (VR) / Reprojected UI plane

**Desktop+**: Advanced desktop access for OpenVR (2021)
<BR> [github/elvissteinjr/DesktopPlus](https://github.com/elvissteinjr/DesktopPlus)
<BR> ![](https://user-images.githubusercontent.com/1193295/96884668-0eb55180-1482-11eb-95da-1f513a9f5a77.png)

**ImGuiVR**: Demo code for using Imgui with OpenVR (2017)
<BR> [github/temcgraw/ImguiVR](https://github.com/temcgraw/ImguiVR) / [video](https://www.youtube.com/watch?v=nlwfn4HJw5E)

**BIMXplorer**: 
<BR> [homepage](https://www.bimxplorer.com/)
<BR> ![](https://user-images.githubusercontent.com/1193295/96884752-25f43f00-1482-11eb-9dd9-9b302c5a2c05.png)

**mpFluid CAVE Front End**
<BR> [github/sariug/mpfluid_cave_frontend](https://github.com/sariug/mpfluid_cave_frontend)
<BR> ![](https://user-images.githubusercontent.com/1193295/96884840-42907700-1482-11eb-9d50-8aef7e88c4a6.png) |  |

# Image manipulation

**imgInspect** (2019)
<BR> [github/CedricGuillemet/imgInspect](https://github.com/CedricGuillemet/imgInspect)
<BR> ![image](https://user-images.githubusercontent.com/8225057/118988474-83515f80-b981-11eb-8ce1-4818ddc3195a.png)

**ImGuiTexInspect**: Advanced, flexible texture inspector (2021-2022)
<BR> [github/andyborrell/imgui_tex_inspect](https://github.com/andyborrell/imgui_tex_inspect) ([discussion](https://github.com/ocornut/imgui/issues/4352), [online demo](https://andyborrell.github.io/imgui_tex_inspect))
<BR> <a href="https://user-images.githubusercontent.com/5911521/126656032-b045b65b-5f42-4065-9c49-c1a22e866a28.png"><img src="https://user-images.githubusercontent.com/5911521/126656032-b045b65b-5f42-4065-9c49-c1a22e866a28.png" alt="Screenshot of ImGuiTexInspect" width="500" /></a>

# 3D manipulation Gizmos

**ImGuizmo**: 3d translation/rotation Gizmo (2016-2022)
<BR> [github/CedricGuillemet/ImGuizmo](https://github.com/CedricGuillemet/ImGuizmo)
<BR> ![](https://user-images.githubusercontent.com/1193295/96868383-41554f00-146e-11eb-84b5-c4264c54532f.png)

**imGuiZMO.quat**: 3d translation/rotation Gizmo (2020)
<BR> [github/BrutPitt/imGuIZMO.quat](https://github.com/BrutPitt/imGuIZMO.quat)
<BR> ![](https://user-images.githubusercontent.com/1193295/96868553-86798100-146e-11eb-872a-44f51ee78117.png)

# Inspectors, Serialization

**ImGui::Auto()**: auto serialize into UI using C++17 (2017)
<BR> [github/Csabix/imgui](https://github.com/Csabix/imgui/tree/master/auto)
<BR> ![](https://user-images.githubusercontent.com/1193295/96878992-c72bc700-147b-11eb-9796-b3c87b543856.png)

**ImQuick**: render UI elements automagically based only on the variable type. (2021)
<BR> [github/martinpetkovski/ImQuick](https://github.com/martinpetkovski/ImQuick)

**imgui-inspect**: [Rust] An inspector UI using imgui in Rust (2021)
<BR> [github/aclysma/imgui-inspect](https://github.com/aclysma/imgui-inspect)

# C++ness

**imgui_stdlib**: InputText() wrappers for C++ standard library (STL) type: std::string (2018-2022)
<BR> [in main repository](https://github.com/ocornut/imgui/tree/master/misc/cpp)

**TextFmt()**: helper to use fmt (2023)
<BR> [pastebin](https://pastebin.com/QCnFhDMu)

**imgui_scoped**: Add some RAII-style wrappers
<BR> [#2096](https://github.com/ocornut/imgui/issues/2096), [#2197](https://github.com/ocornut/imgui/pull/2197)

**imgui_sugar**: C++11 syntactic sugar for Dear ImGui with RAII guards (2021-2022)
<BR> [github/mnesarco/imgui_sugar](https://github.com/mnesarco/imgui_sugar)

**imguiwrap**: CMake wrapper for imgui and C++17+ based RAII bindings, and helpers for bootstrapping simple projects.
<BR> [github/kfsone/imguiwrap](https://github.com/kfsone/imguiwrap)


# Miscellaneous

**Combos with custom filtering and preview**
<BR> [issue #1658](https://github.com/ocornut/imgui/issues/1658)

**imgui_memory_editor** (2017-2022)
<BR> [github/ocornut/imgui_club](https://github.com/ocornut/imgui_club)
<BR> ![](https://user-images.githubusercontent.com/1193295/96868227-081cdf00-146e-11eb-996b-35134ba8bd3c.png)

**ImZoomSlider**: Range/Zooming Slider (2020-20220
<BR> [github/CedricGuillemet/ImGuizmo](https://github.com/CedricGuillemet/ImGuizmo)

**Splitters**
<BR> [issue #319](https://github.com/ocornut/imgui/issues/319)
<BR> ![](https://user-images.githubusercontent.com/8225057/97189595-0ff9bd80-17a5-11eb-871a-d423d1ecffb1.png)

**Slider 2D and Slider 3D**
<BR> [issue #3484](https://github.com/ocornut/imgui/issues/3484)
<BR> ![](https://user-images.githubusercontent.com/1193295/96874705-bb89d180-1476-11eb-8640-43805b800ebf.png)

**ImGui-2D-HArrow** :2D Mobile Components
<BR> [github/Half-People/ImGui-2D-HArrow](https://github.com/Half-People/ImGui-2D-HArrow)
<BR> ![](https://user-images.githubusercontent.com/56476339/215034490-99ab6ae4-cdc5-44bc-a863-eeb8f7de8e18.gif)


**imgui-notify**: header-only wrapper made to create notifications** (2021)
<BR> [github/patrickcjk/imgui-notify](https://github.com/patrickcjk/imgui-notify)
<BR> ![](https://user-images.githubusercontent.com/8225057/122738845-a625ab00-d282-11eb-8c9f-d4c7138cf815.png)

**ImHotKey**: hotkey editor
<BR> [github/CedricGuillemet/ImHotKey](https://github.com/CedricGuillemet/ImHotKey)
<BR> ![](https://user-images.githubusercontent.com/1193295/96875055-14596a00-1477-11eb-93bb-74d977fbf7e3.png)

**IP Entry Box**
<BR> [issue #388](https://github.com/ocornut/imgui/issues/388)
<BR> ![](https://user-images.githubusercontent.com/1193295/96875257-4f5b9d80-1477-11eb-9789-dbc203d8a3f4.png)

**Pie Menu**
<BR> [issue #434](https://github.com/ocornut/imgui/issues/434)
<BR> ![](https://user-images.githubusercontent.com/1193295/96875448-82059600-1477-11eb-93be-db904ae920a8.png)

**nnview**: a neural network viewer
<BR> [github/lighttransport/nnview](https://github.com/lighttransport/nnview)
<BR> ![](https://user-images.githubusercontent.com/1193295/96875679-ca24b880-1477-11eb-8d4c-022166c8a427.png)

**ImGui Command Palette** (2022)
<BR> [github/hnOsmium0001/imgui-command-palette](https://github.com/hnOsmium0001/imgui-command-palette)
<BR> ![](https://user-images.githubusercontent.com/36975818/147279807-5123e130-80f5-4f82-bab4-099a29b7ca95.png)

Also [Useful Widgets](https://github.com/ocornut/imgui/labels/useful%20widgets) Tag in Issues.

# Third party repos

**Flix01's ImGui-Addons**: file dialog, date picker, listview, toolbar etc.
<BR> [github/Flix01/imgui](https://github.com/Flix01/imgui/wiki/ImGui-Addons-Branch-Home)
<BR> ![](https://user-images.githubusercontent.com/1193295/96885173-a4e97780-1482-11eb-84f6-637b1f2bd274.png)

**@leiradel's snippets**
<BR> [github/leiradel/ImGuiAl](https://github.com/leiradel/ImGuiAl/)

**HImGuiEditor (The purpose is to make editing ImGui clearer and easier for users. thus speeding up development)**
<BR> [issue #6157](https://github.com/ocornut/imgui/issues/6157)
<BR>![Image](https://user-images.githubusercontent.com/56476339/218251960-8055e05d-9af6-4c8c-a9d3-3a5e26a758c9.gif)

**@nem0's snippets** (in imgui_user.* files)
<BR> [github/nem0/LumixEngine](https://github.com/nem0/LumixEngine/tree/master/external/imgui)
<BR> ![](https://user-images.githubusercontent.com/1193295/96885426-dd895100-1482-11eb-9f0f-f52a9f13eb18.png)

**@aoterodelaroza's snippets**
<BR> [github/aoterodelaroza/imgui-goodies](https://github.com/aoterodelaroza/imgui-goodies)
<BR> ![](https://user-images.githubusercontent.com/1193295/96885795-3a850700-1483-11eb-99b0-8d3416796968.png)

**MetricsGui**: controls for displaying performance metrics
<BR>[github/GameTechDev/MetricsGui](https://github.com/GameTechDev/MetricsGui)
<BR> ![](https://user-images.githubusercontent.com/1193295/96885983-6e602c80-1483-11eb-9006-44b46d994730.png)

**nakedeyes' UnrealImGuiTools**: game agnostic ImGui tools and utilities for Unreal Engine game development.
<BR>[github/UnrealImGuiTools](https://github.com/nakdeyes/UnrealImGuiTools)
<BR> <img width="500" alt="image" src="https://user-images.githubusercontent.com/15803559/178168651-b0a98998-bfd0-443b-a741-80d58d95fdb1.png">

----

Also see [Gallery Threads](https://github.com/ocornut/imgui/labels/gallery) and [Software Using Dear ImGui](https://github.com/ocornut/imgui/wiki/Software-using-dear-imgui) for references of other software which may be open-sourced.
