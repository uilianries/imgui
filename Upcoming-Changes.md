Last updated 2022/12.
This is a higher-level list of intent. Refer to [Issues](https://github.com/ocornut/imgui/issues) and TODO.txt for a more detailed list.

## Viewport

- Improve [Multi-Viewports](https://github.com/ocornut/imgui/wiki/Multi-Viewports) feature toward merging in Master (~2.00) ([#1542](https://github.com/ocornut/imgui/issues/1542)).

## DPI

- Better DPI support (current solution is for user to load font + scale style according to DPI). ([#1676](https://github.com/ocornut/imgui/issues/1676))

## Navigation, Controls

- Improve gamepad and keyboard controls. ([#787](https://github.com/ocornut/imgui/issues/787))
- Inputs: Input ownership and routing system (pushed to imgui_internal on 2022/12).
- Shortcuts: menus/global-style shortcuts (internal proof-of-concept ready 2022/12)
- Shortcuts: alt-style local shortcuts.
- Menus: once menus are able to handle their shortcuts (aka recursing in non-visible menus) we could envision Mac-style menu searching.

## Docking

- Improve/rewrite [Docking](https://github.com/ocornut/imgui/wiki/Docking) toward merging in 2.0. ([#2109](https://github.com/ocornut/imgui/issues/2109))

## Text/Fonts

- Finish work/design on backend texture update ([#3761](https://github.com/ocornut/imgui/issues/3761).
- Incremental font atlas updates.
- Rewrite better text primitives.

## Styling

- Improve styling support (easier to add more colors, basic inheritance system, cache float4->ImU32 conversions).
- Improve basic render primitives (allow for gradients, etc.).
- Optimize basic render primitives (e.g. using 8-way texture for curved shapes, borders, circles) to reduce CPU  +vertices cost.

## Bindings

- Improve [dear_bindings](https://github.com/dearimgui/dear_bindings) to ease the generation of language bindings (e.g. C).

## Automation, Tests

- Improve the [Dear ImGui Test Engine](https://github.com/ocornut/imgui_test_engine).

## Misc

- Selection: Finish/merge range-selection/multi-selection API (1.90?), to support Shift+Click, Shift+Arrow, etc. with clipping.
