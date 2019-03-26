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

### Using breakpoints
Using debugger breakpoints can be tedious in an interactive application dealing with lots of data. Even more so as the state of the application may be so reliant on mouse and keyboard inputs. One convenient trick is filter breakpoint based on custom conditions, e.g checking for the Alt key modifier to be pressed:

```
if (ImGui::GetIO().KeyAlt)
    printf(""); // Set a debugger breakpoint here!
```

So you can setup your UI state for debugging (open windows, mouse position, active action etc.) and then only when you press ALT your breakpoint will trigger.
