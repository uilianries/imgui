### Using breakpoints
Using debugger breakpoints can be tedious in an interactive application dealing with lots of data. Even more so as the state of the application may be so reliant on mouse and keyboard inputs. One convenient trick is filter breakpoint based on custom conditions, e.g checking for the Alt key modifier to be pressed:

`if (ImGui::GetIO().KeyAlt)`
`    printf(""); // Set a debugger breakpoint here!`

So you can setup your UI state for debugging (open windows, mouse position, active action etc.) and then only when you press ALT your breakpoint will trigger.
