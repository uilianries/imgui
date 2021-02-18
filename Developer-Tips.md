If you are working on Dear ImGui codebase:

### Metrics
The Metrics window exposes lots of information about the library state.

### Item Picker
The Item Picker will allow you to pick an item with the mouse and have Dear ImGui break within the call-stack of that item. This is useful if you have large UI / codebase and you would to easily find out where some UI item is emitted. 
You can find it in _Metrics>Tools>Item Picker_. Also see [#2673](https://github.com/ocornut/imgui/issues/2673).

![Item Picker](https://user-images.githubusercontent.com/8225057/61412736-7d2e5b80-a89e-11e9-9bb3-54c097025abe.png)

### Visual debugging
You can use drawlist primitives on the foreground drawlist, e.g. `GetForegroundDrawList()->AddRectFilled(...)` to bypass clipping of the current window's drawlist.

### Logging
You can use the `IMGUI_DEBUG_LOG` macro (declared in `imgui_internal.h`) to easily print text to the console while including the current frame counter, which is very often useful in log.

### Using breakpoints
Using debugger breakpoints can be tedious in an interactive application dealing with lots of data. Even more so as the state of the application may be so reliant on mouse and keyboard inputs. One convenient trick is filter breakpoint based on custom conditions, e.g checking for the Alt key modifier to be pressed:

```
if (ImGui::GetIO().KeyAlt)
    printf(""); // Set a debugger breakpoint here!
```

So you can setup your UI state for debugging (open windows, mouse position, active action etc.) and then only when you press ALT your breakpoint will trigger.

### Continuous integration
Branches pushed publicly will have [build actions](https://github.com/ocornut/imgui/actions) run on them.

### Automation and regression testing system
We are using a large suite of automated tests (still unpublished, see [#435](https://github.com/ocornut/imgui/issues/435)), recurrent contributors can get access to it.

### Using Natvis file for Visual Studio debugging
The `misc/natvis/imgui.natvis` file may be included in your project to provide support for dear imgui types in the debugger (e.g. expanding of `ImVector<>` arrays).

### Using static analysis with PVS-Studio:
I am using [PVS-Studio](https://www.viva64.com/en/pvs-studio/) (Viva64 had kindly provided a licence to use with free software products) for static code analysis and it's been extremely helpful in reducing the amount of errors or confusing code.

_run_pvs_studio.bat_:
```
@echo off
set PVS_DIR=C:\Program Files (x86)\PVS-Studio
set WORK_DIR=C:\Work\imgui_dev\pvs_studio
set PROJ_DIR=C:\Work\imgui\examples\example_win32_directx11
set PROJ_NAME=example_win32_directx11
"%PVS_DIR%\PVS-Studio_Cmd.exe" -r -t "%PROJ_DIR%\%PROJ_NAME%.vcxproj"
mkdir "%WORK_DIR%\output"
"%PVS_DIR%\PlogConverter.exe" -a GA:1,2;OP:1 -t Html,FullHtml,Txt,Totals "%PROJ_DIR%\%PROJ_NAME%.plog" -o "%WORK_DIR%\output"
del "%PROJ_DIR%\%PROJ_NAME%.plog"
echo ---- Totals:
type "%WORK_DIR%\output\%PROJ_NAME%.plog_totals.txt"
start "" "%WORK_DIR%\output\fullhtml\index.html"
```
