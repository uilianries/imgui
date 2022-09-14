Last updated 2022/09.
This is a higher-level list of intent. Refer to TODO.txt for a more detailed list.

## Viewport

- Improve Viewport branch toward merging in Master (1.90? 2.00?) ([#1542](https://github.com/ocornut/imgui/issues/1542)).

## DPI

- Better DPI support (current solution is for user to load font + scale style according to DPI). ([#1676](https://github.com/ocornut/imgui/issues/1676))

## Navigation, Controls

- Improve gamepad and keyboard controls. ([#787](https://github.com/ocornut/imgui/issues/787))
- Inputs: Input ownership and routing system (2022).
- Shortcuts: menus/global-style shortcuts.
- Shortcuts: alt-style local shortcuts.
- Menus: once menus are able to handle their shortcuts (aka recursing in non-visible menus) we could envision Mac-style menu searching.

## Docking

- Improve/rewrite Docking (merge 2.00?) ([#2109](https://github.com/ocornut/imgui/issues/2109))

## Text/Fonts

- Finish work/design on backend texture update ([#3761](https://github.com/ocornut/imgui/issues/3761).
- Incremental font atlas updates.
- Rewrite better text primitives.

## Styling

- Improve styling support (easier to add more colors, basic inheritance system, cache float4->ImU32 conversions).
- Improve basic render primitives (allow for gradients, etc.).
- Optimize basic render primitives (e.g. using 8-way texture for curved shapes, borders, circles) to reduce CPU  +vertices cost.

## Bindings

- Release "dear_bindings" ease the generation of language bindings (e.g. C), as an "v3" alternative to https://github.com/cimgui/cimgui

## Automation, Tests

- Release Dear ImGui Test Engine (Q3-Q4 2022).

## Misc

- Selection: Finish/merge range-selection/multi-selection API (1.90?), to support Shift+Click, Shift+Arrow, etc. with clipping.
