Tips for when working on Dear ImGui codebase.

Also see [Tips](https://github.com/ocornut/imgui/wiki/Tips), [Debug Tools](https://github.com/ocornut/imgui/wiki/Debug-Tools).

### Automation and regression testing system

Get yourself familiarized with running the [Dear ImGui Test Suite](https://github.com/ocornut/imgui_test_engine). You can use it to:
- catch regression and contract changes. 
- understand when some code is exercised or which condition may be leading to a given state. e.g. "can this value ever be NULL?": add a break-point or assert and run the Test Suite, you are likely to find out!

Making a change and running the Test Suite is a good way to understand possible side-effects of that change.

When fixing bugs or adjusting some esoteric features, adding a new test case is generally useful.

### Metrics
The Metrics window exposes lots of information about the library state. See [[Debug Tools]].

### Logging
You can use the `IMGUI_DEBUG_LOG_XXX` macros (declared in `imgui_internal.h`) to easily print text to console and in 'Debug Log' while including the current frame counter, which is very often useful in log.

### Using breakpoints
Using debugger breakpoints can be tedious in an interactive application dealing with lots of data. Even more so as the state of the application may be so reliant on mouse and keyboard inputs. One convenient trick is filter breakpoint based on custom conditions, e.g checking for the Alt key modifier to be pressed:

```
if (ImGui::GetIO().KeyAlt)
    printf(""); // Set a debugger breakpoint here!
```

So you can setup your UI state for debugging (open windows, mouse position, active action etc.) and then only when you press ALT your breakpoint will trigger.

### Continuous integration
Branches pushed publicly will have [build actions](https://github.com/ocornut/imgui/actions) run on them.

### Using Natvis file for Visual Studio debugging
The `misc/natvis/imgui.natvis` file may be included in your project to provide support for Dear ImGui types in the debugger (e.g. expanding of `ImVector<>` arrays).

### Using static analysis with PVS-Studio:
I am using [PVS-Studio](https://www.viva64.com/en/pvs-studio/) (Viva64 had kindly provided a license to use with free software products) for static code analysis and it's been extremely helpful in reducing the amount of errors or confusing code.

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
