**Backends/Bindings**: a piece of code that connects your OS/platform/windowing system, graphics API or programming language to Dear ImGui. In the `examples/` folder we provide a bunch of `imgui_impl_xxxx` files which are backends for variety of platforms and graphics API. Many other [third-party bindings](https://github.com/ocornut/imgui/wiki/Bindings) exists.

**Demo**: the demo code in `imgui_demo.cpp`, which main entry point is the `ImGui::ShowDemoWindow()` function.

**Docking**: refer to the feature (currently available in the `docking` branch) where multiple windows can be combined with each others, creating tab bars, or layed out next to each others.

**Draw command, ImDrawCmd**: refer to one item within an `ImDrawList`. One draw command generally map to one draw call in the underlying graphics API. Some draw commands hold callbacks or special functions that don't necessarily map to an actual draw call in the graphics API.

**Draw list, ImDrawList**: refer to the low-level rendering API which you can use to submit shapes (such as rectangles, lines, circles or text elements). The ImGui API uses the ImDrawList API to draw elements. You can easily access the drawlist of the current ImGui window using `ImGui::GetWindowDrawList()` or access special drawlists such as `ImGui::GetBackgroundDrawList()` (drawn before every ImGui windows) or `ImGui::GetForegroundDrawList()` (drawn after every ImGui windows). A draw list is generally comprised of multi draw commands.

**Examples**: examples application in the sub-folders of `examples/`. An example application generally combines one or two backends + dear imgui code + a main.cpp file to form a running application.

**Font atlas**: a font atlas manage multiple fonts, which for performance reasons are generally rasterized and packed together into a single graphics texture. The font atlas also contains graphics data that are used by ImGui and ImDrawList.

**Item**: (same as Widget): a single ImGui element (e.g. a `ImGui::Button()` or `ImGui::Text()` call).

**Navigation**: refer to the subsystem in charge of allowing full control of the UI using Gamepad or Keyboard inputs. Initially Dear ImGui was mostly using mouse inputs and the "navigation" feature allowed directional navigation within a set of widgets.

**Metrics**: refer to the confusingly named `Dear ImGui Metrics` window, which main entry point is the `ImGui::ShowMetricsWindow()` function. The Metrics window exposes lots of internal information about the state of your Dear ImGui context. Using it can help you debug and understand many problems you may have with Dear ImGui. It may also help you better understand how Dear ImGui works.

**Multi-Viewports**: refer to the feature (currently available in the `docking` branch) where Dear ImGui window can easily be moved outside the boundaries of your main application window. The multi-viewports feature provides an interface to interact with bindings in order to create its own application windows to host the floating Dear ImGui windows.

**Widgets**: (same as Item): a single ImGui element (e.g. a `ImGui::Button()` or `ImGui::Text()` call).
