Not a dated roadmap yet, mostly a list of some of the big upcoming tasks.
Aside from those tasks, there are hundreds of worthy smaller tasks.

- Navigation: finish and merge in the nav branch (gamepad control support, toward keyboard control support)
- ColorPicker: finish and merge in Color picker. Make it provide for user to provide their own.
- Tabs: re-ordering, custom menus, order access/saving.
- Columns: header, re-ordering, sizing policy, settings access/saving, sorting, recurse. Basically fix the broken columns.
- Docking: investigate the various existing solutions, provide an officially maintained extension.
- Keyboard shortcut systems: alt-style local shortcuts, menus/global-ey shortcuts.
- Remote: Provide an officially maintained, ready to use remote imgui solution (probably, based on https://github.com/JordiRos/remoteimgui).
- Testing, Doc: Introduce a testing/documentation framework. Reduce regression, make it easier for anyone to contribute, reduce dependencies on me (ocornut).
- Layout: various layout helpers/improvements (alignment, layout variations for common widgets).
- Improve Combo, ListBox to allow variety of inputs (e.g. sparse/loose lists).
- Plot/graph: overlay multiple graphs, various helpers and type of graphs, grids, panning/zooming, combine low-level elements to create complex graphs, etc.
- Internals: Improve internals toward making custom widget/code more stable, improve forward compatibility.
- Styling: Improve styling support, better default styles (toward being good enough so that people don't need to care/worry about styling. Not aiming at making imgui end-user ui for games look & feel, but good enough for tools).
- Improve usage of multiple context or multi-threaded situations.
- Rewrite and improve the multi-line text editor (many fixes and desirable features)
- Optimizations: E.g. using texture cache for curved shapes, circles, etc. to reduce vertices+CPU cost rendering rounded elements.
- Text: Extension to provide basic form of rich/markup text display.
- Text: Make the font atlas system dynamic to ease scaling and avoid baking large range of characters for foreign languages.
- Demos: Add more demos/examples!
- Support: Provide support to both expert and novice users. Dear ImGui is used by many people learning C++ and although their questions are sometimes misled, keeping younger developers in the C++ ecosystem is healthy and useful for everyone.
