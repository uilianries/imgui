(work in progress)

## Index

- [General Terms](#general-terms)
- [Multi-Viewports Terms](#multi-viewports Terms)

## General Terms

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

## Multi-Viewports Terms

Note: when talking about issues related to the multi-viewports feature, always try to remove ambiguity by specifying e.g. "_Dear ImGui Window_" vs "_Platform Window_".

**Desktop**: the area managed by the Operating System or Window Manager and covers all _Platform Monitors_.

**Platform**: refer to the low-level system used to interface with native windows: it could be an Operating System library (Win32) or a cross-platform library (such as SDL, GLFW, Allegro).

**Platform Backend**: refer to the piece of glue code used to have Dear ImGui interact with a given platform (e.g. `imgui_impl_glfw.cpp` file). This code typically creates and destroy _Platform Windows_ associated to each _Viewport_, and setup the _Platform Decorations_ based on _Viewport_ flags.

**Platform Decoration**: refer to the frame and title bar managed and displayed by the Operating System or Widnow Manager.

**Platform Monitor**: refer to the representation of a monitor. On a modern OS, each monitor are associated to a non-overlapping set of coordinates (position, size), a work area (main area minus OS task bar) and a DPI scaling factor. Dear ImGui takes advantage of _Platform Monitor_ knowledge for certain tasks (for exemple, tooltip windows gets clamped to fit within a single _Platform Monitor_ and not straddle multiple monitors).

**Platform Window**: a window managed by the Operating System. This is typically associated to a framebuffer, a swap chain and the machinery to perform 3D rendering via some graphics API.

**ImGui Decoration**: refer to the frame and title bar managed and displayed by _ImGui Windows_.

**ImGui Window**: a window inside of Dear ImGui.

**Host Viewport**: A _Host Viewport_ can contains multiple root _ImGui Windows_. Currently the _Main Viewport_ is always a _Host Viewport_. In the future we would like to allow application to create 0, 1 or more _Host Viewports_. When a _Host Viewport_ is moved, all the _Dear ImGui Windows_ it contains gets moved along with it. By default, any _ImGui Window_ overlapping a _Host Viewport_ will be merged into it. Setting `io.ConfigViewportsNoAutoMerge` disable that behavior, so every _ImGui Window_ will be hosted by their own unique _Single-Window Viewport_.

**Single-Window Viewport, Owned Viewport**: a _Viewport_ owned by a single root _ImGui Window_. In the typical setup, dragging a _ImGui Window_ outside the boundary of a _Host Viewport_ will create a _Single-Window Viewport_ for the purpose of allowing the _ImGui Window_ to be displayed anywhere on the _Desktop_.

**Main Viewport**: Due to common usage and backward compatibility reason, the system currently enforce the creation of one _Main Viewport_ which is typically the main application window created by the user application. The _Main Viewport_ is also a _Host Viewport_. In most traditional application, the _Main Viewport_ has _Platform Decorations_ enabled when not maximized, and has _Platform Decorations_ disabled when fullscreen. In the future we would like to completely remove the concept of a "Main Viewport" and instead allow the application to freely create 0, 1 or more _Host Viewports_. Most games applications will create 1 of them, whereas most desktopey applications are expected to create 0 of them. Using this scheme, an application creating no _Host Viewport_ would have every _ImGui Window_ showing inside an individual _Platform Window_ with _Platform Decorations_ disabled.

**Viewport**: The Dear ImGui representation of a _Platform Window_. When a _Viewport_ is active, Dear ImGui creates a _Platform Window_ for it. Whether the _Platform Window_ has _Platform Decorations_ enabled currently depends on the `io.ConfigViewportsNoDecoration` flag which gets turned into a `ImGuiViewportFlags_NoDecoration` for the _Platform Backend_ to honor.
