(work in progress) Also see [[Tips]].

### Metrics/Debugger window

Many internal state and tools are exposed in the Metrics window. To access the Metrics window:
- Call `ShowMetricsWindow()`.
- Or from the Demo window you can find it in the Tools menu.
They will help you understand how Dear ImGui works, and can help you diagnose problems.

![Metrics](https://user-images.githubusercontent.com/8225057/191290900-87c7f347-d459-4192-8894-689c11b44e65.png)

![Fonts debugging](https://user-images.githubusercontent.com/8225057/135429892-0e41ef8d-33c5-4991-bcf6-f997a0bcfd6b.png)

![debug tools](https://user-images.githubusercontent.com/8225057/174845561-ee9ba6ad-9f48-478c-944d-85334aae0af7.png)
_Some of the debug tools_

### Debug Log

![Debug Log](https://user-images.githubusercontent.com/8225057/191291345-9bf5fae2-ff0f-462a-af4c-d85aaaf36318.png)

### Stack Tool

![stack_tool_03](https://user-images.githubusercontent.com/8225057/136235657-a0ea5665-dcd1-423f-9be6-dc3f8ced8f12.png)

### Item Picker

The Item Picker will allow you to pick an item with the mouse and have Dear ImGui break within the call-stack of that item. This is useful if you have large UI / codebase and you would to easily find out where some UI item is emitted. 
You can find it in _Metrics>Tools>Item Picker_. Also see [#2673](https://github.com/ocornut/imgui/issues/2673).

![Item Picker](https://user-images.githubusercontent.com/8225057/61412736-7d2e5b80-a89e-11e9-9bb3-54c097025abe.png)
