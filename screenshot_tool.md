## Screenshot tool

Simple tool to help creating screenshot of ImGui windows (requires OpenGL + stb_image_write.h)

![Screenshot tool](https://cloud.githubusercontent.com/assets/8225057/9546820/d0934d32-4d8d-11e5-8b3e-a8b852361bcb.PNG)

### Source

```
#define _CRT_SECURE_NO_WARNINGS
#include "imgui.h"
#define IMGUI_DEFINE_MATH_OPERATORS
#include "imgui_internal.h"

#include <examples/libs/glfw/include/GLFW/glfw3.h>
#define STB_IMAGE_WRITE_IMPLEMENTATION
#include "stb_image_write.h"

void ShowScreenshotsWindow(bool* open)
{
    if (!ImGui::Begin("Screenshots", open))
    {
        ImGui::End();
        return;
    }

    ImGuiState& g = *GImGui;

    static ImGuiStorage storage;
    static float border = 16.0f;
    bool capture = ImGui::Button("ALT+C: Capture");
    ImGui::SliderFloat("border", &border, 0.0f, 32.0f, "%.0f");

    ImRect visible_rect(ImVec2(0,0), g.IO.DisplaySize);
    ImRect bounds_rect;

    for (int i = 0; i < g.Windows.size(); i++)
    {
        ImGuiWindow* window = g.Windows[i];
        if (!window->Active && !window->WasActive)
            continue;
        if (window->Flags & ImGuiWindowFlags_Popup)
        {
            bounds_rect.Add(window->Rect());
            continue;
        }
        if (window->Flags & ImGuiWindowFlags_ChildWindow)
            continue;

        ImGui::PushID(window);
        bool* p_selected = (bool*)storage.GetIntRef(window->RootWindow->ID, 0);
        g.DisableHideTextAfterDoubleHash++;     // Not exposed (yet). Disable processing that hides text after '##' markers.
        ImGui::Checkbox(window->Name, p_selected);
        g.DisableHideTextAfterDoubleHash--;
        if (*p_selected)
            bounds_rect.Add(window->Rect());
        ImGui::SameLine(120);
        ImGui::PushItemWidth(200);
        ImGui::DragFloat2("Size", &window->SizeFull.x, 0.05f, 0.0f, 0.0f, "%.0f");
        ImGui::PopItemWidth();
        ImGui::PopID();
    }

    bounds_rect.Expand(border);

    char buf[128];
    sprintf(buf, "%.0f x %.0f", bounds_rect.GetWidth(), bounds_rect.GetHeight());
    g.OverlayDrawList.AddText(ImGui::GetWindowFont(), ImGui::GetWindowFontSize(), ImVec2(1,1), ImColor(255,255,255), buf);
    g.OverlayDrawList.AddRect(bounds_rect.Min-ImVec2(1,1), bounds_rect.Max+ImVec2(1,1), 0xFFFFFFFF);

    capture |= (ImGui::GetIO().KeyAlt && ImGui::IsKeyPressed(ImGui::GetKeyIndex(ImGuiKey_C)));
    if (capture)
    {
        int w = (int)bounds_rect.GetWidth(), h = (int)bounds_rect.GetHeight();
        unsigned char* pixels = new unsigned char[3 * w * h];
        glPixelStorei(GL_PACK_ALIGNMENT, 1);
        glReadPixels((int)bounds_rect.Min.x, (int)ImGui::GetIO().DisplaySize.y - (int)bounds_rect.Max.y, w, h, GL_RGB, GL_UNSIGNED_BYTE, pixels);
        unsigned char* line_tmp = new unsigned char[3 * w];
        unsigned char* line_a = pixels;
        unsigned char* line_b = pixels + (3 * w * (h - 1));
        while (line_a < line_b)
        {
            memcpy(line_tmp, line_a, w * 3);
            memcpy(line_a, line_b, w * 3);
            memcpy(line_b, line_tmp, w * 3);
            line_a += w * 3;
            line_b -= w * 3;
        }

        stbi_write_png("out.png", w, h, 3, pixels, w * 3);
        delete[] pixels;
        delete[] line_tmp;
    }

    ImGui::End();
}

```