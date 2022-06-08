**(THIS DRAFT HAS BEEN ABANDONED BY ITS CREATOR)**

# Text
## ImGui::Text

Draws formatted text. The format options are like `printf`.
### Function Signature
```c++
IMGUI_API void Text(const char* fmt, ...);
```
### Example
```c++
ImGui::Text("Hello world %f", 42);
```

# Main
## ImGui::Button
Draws a button and returns whether it was clicked or not.
### Function Signature
```c++
IMGUI_API bool Button(const char* label, const ImVec2& size = ImVec2(0, 0));
```
### Example
```c++
if (ImGui::Button("Button"))
{
    printf("Button Clicked");
}
```

# Combo Box

# Drag Sliders

# Regular Sliders

# Trees

# Selectables

# Data plotting

# Menus

# Tooltips

# Tables