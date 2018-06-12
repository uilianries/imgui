## Viewport

- Improve Viewport branch toward merging in Master.

## DPI

- Better DPI support (current solution is for user to load font + scale style according to DPI).

## Navigation, Controls

- Improve gamepad and keyboard controls.
- Shortcuts: menus/global-style shortcuts.
- Shortcuts: alt-style local shortcuts.
- Menus: once menus are able to handle their shortcuts (aka recursing in non-visible menus) we could envision Mac-style menu searching.

## Tabs, Docking

- Tabs: with re-ordering, custom menus, persistent orders, also usable locally aside from docking (WIP).
- Docking: full-featured docking solution (WIP).

## Columns, Table

- Redesign Columns/Table API
- With e.g.: Header, re-ordering, sizing policy, persistence, sorting, scrolling with visible headers, etc.

## Styling

- Improve styling support (easier to add more colors, basic inheritance system, cache float4->ImU32 conversions).
- Improve basic render primitives (gradients, etc.).
- Optimize basic render primitives (e.g. using 8-way texture for curved shapes, borders, circles) to reduce CPU  +vertices cost.
- Better default styles.

## Remote

- Remote: Provide an officially maintained, ready to use remote imgui solution (e.g. based on https://github.com/JordiRos/remoteimgui).

## Bindings

- Renderer: Add Metal renderer.
- Renderer: Decide on texture handling for Vulkan, DirectX12 renderer.
- Platform: GLFW: Assist toward GLFW support what we need for full portable multi-viewport support (remaining: https://github.com/glfw/glfw/issues/1236, https://github.com/glfw/glfw/pull/989, https://github.com/glfw/glfw/issues/427)
- Languages: Provide/maintain a script to ease the generation of language bindings (e.g. C).

## Testing, Doc

- Introduce a testing/documentation framework. Reduce regression, make it easier for anyone to contribute, reduce dependencies on @ocornut.

## Misc

- Widgets: Design a way to represent and interact "mixed values" for when a multi-selection set have differing values and the widget represents them.
- Selection: Range-selection/multi-selection API (to support Shift+Click, Shift+Arrow, etc.).
- Layout: various layout helpers/improvements (alignment, layout variations for common widgets).
- Improve Combo, ListBox to allow variety of inputs (e.g. sparse/loose lists). Make it more natural to create own widgets of that sort with higher guarantee of forward compatibility.
- Plot/graph: overlay multiple graphs, various helpers and type of graphs, grids, panning/zooming, combine low-level elements to create complex graphs, etc.
- Internals: Improve internals toward making custom widget/code more stable, improve forward compatibility.
- Improve usage of multiple context or multi-threaded situations.
- Rewrite and improve the multi-line text editor (many fixes and desirable features)
- Text: Extension to provide basic form of rich/markup text display.
- Text: Make the font atlas system dynamic to ease scaling and avoid baking large range of characters for foreign languages.
- Demos: Add more demos/examples!
- Support: Provide support to both expert and novice users. Dear ImGui is used by many people learning C++ and although their questions are sometimes misled, keeping younger developers in the C++ ecosystem is healthy and useful for everyone.
