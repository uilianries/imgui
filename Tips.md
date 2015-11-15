**Tip: use Begin/BeginChild to put yourself into the context of another window prior or after outputting to it**<br>
https://github.com/ocornut/imgui/issues/270

An interesting trick that isn't obvious is that you can use Begin() just to put yourself into the context of that window. So here I want to react to the user inputting an address to scroll to, I use BeginChild() again on the child that I've already drawn so I can use SetScrollFromPosY() on it.

```
ImGui::BeginChild("##scrolling", ImVec2(0, -ImGui::GetItemsLineHeightWithSpacing()));
// ...(draw main content)
ImGui::EndChild();

// And then much later in the main window, get back into child context to change scrolling offset
ImGui::BeginChild("##scrolling");
ImGui::SetScrollFromPosY(ImGui::GetCursorStartPos().y + (goto_addr / Rows) * line_height);
ImGui::End();
```
