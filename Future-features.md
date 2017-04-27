(last updated apr 2017)

Not a dated roadmap yet, mostly a list of some of the big upcoming tasks.
Aside from those tasks, there are hundreds of worthy smaller tasks, so dev is likely to be 50% new features 50% improving/fixing existing features.

Experienced users have been achieving many of those things themselves in one form or another (sometimes using custom extensions / fork). I would like those features to be standard, natural first-class citizens of the Dear ImGui ecosystem.

I _think_ there is a sort of urgency. If those features are not standardized, more people will fork and implement their own solution and it will be hard for them to come back to master. It's been happening already. It's not the end of the world, but the value of Dear ImGui is that it decently solves problems that everyone have. It's be preferably if those solutions where shared.

I have just shipped [my game](http://www.TheDragonsTrap.com) this month, and working on Steam version now. After that I would be free and I would like to cease this timing opportunity to gather funds to focus on Dear ImGui for a while. If your company uses it, there is maybe something you can do to contribute and make it happens. If I cannot make a living out of it I may have to return making games, please save me from this fate.

## Screenshots

[LumixEngine](https://cloud.githubusercontent.com/assets/153526/17481789/18b71916-5d7f-11e6-9726-9e17dec1f3b4.png)
/ [An Animation editor](https://cloud.githubusercontent.com/assets/814772/17825130/ee09ace8-661a-11e6-80b5-c315fa4eaaa6.png)
/ [A Sprite editor](https://cloud.githubusercontent.com/assets/16607879/25135067/8d2c8864-2451-11e7-904e-e525e2736417.png)
/ [Graph based noise tool](https://cloud.githubusercontent.com/assets/577713/24189405/175f3a86-0ee5-11e7-8302-768de7fc2a16.png)
/ [Styling, node based tool](https://cloud.githubusercontent.com/assets/12642134/23952212/fa85c398-0990-11e7-8621-b1adbb71fab5.jpg)
/ [A game editor](https://cloud.githubusercontent.com/assets/4952023/13963091/3f8caedc-f021-11e5-8709-90c8ea7df1c0.png)
/ [Boundless](https://cloud.githubusercontent.com/assets/8225057/17051226/d37e7f86-4ff7-11e6-8f83-64808debb7e1.png)
/ [Docking](https://cloud.githubusercontent.com/assets/12642134/18140511/288541a8-6fb6-11e6-8423-72b4c808016d.gif)
/ [CADrays](https://cloud.githubusercontent.com/assets/1812916/23785566/c643057c-0581-11e7-9a49-1cd3bdbad830.jpg)
/ [The Dragon's Trap](https://cloud.githubusercontent.com/assets/8225057/20628927/33e14cac-b329-11e6-80f6-9524e93b048a.png)
/ [FishEngine](https://raw.githubusercontent.com/yushroom/FishEngine/master/Snapshot/20161129.png)
/ [Overgrowth](https://cloud.githubusercontent.com/assets/1066954/22568057/24c1dcc4-e947-11e6-8c97-870d8e70a380.jpg)

## Feature List

- Navigation: finish and merge in the nav branch (gamepad control support, toward keyboard control support)
- ColorPicker: finish and merge in Color picker. Make it provide for user to provide their own.
- Tabs: re-ordering, custom menus, order access/saving.
- Columns: header, re-ordering, sizing policy, settings access/saving, sorting, recurse. Basically fix the broken columns.
- Docking: investigate the various existing solutions, provide an officially maintained extension.
- Keyboard shortcut systems: alt-style local shortcuts, menus/global-ey shortcuts.
- Remote: Provide an officially maintained, ready to use remote imgui solution (probably, based on https://github.com/JordiRos/remoteimgui).
- Testing, Doc: Introduce a testing/documentation framework. Reduce regression, make it easier for anyone to contribute, reduce dependencies on me (ocornut).
- Layout: various layout helpers/improvements (alignment, layout variations for common widgets).
- Improve Combo, ListBox to allow variety of inputs (e.g. sparse/loose lists). Make it more natural to create own widgets of that sort with higher guarantee of forward compatibility.
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
