### Example

Dear ImGui can load TTF/OTF fonts. UTF-8 is supported for text display and input. Here using Arial Unicode font to display Japanese. Initialize custom font with:
Code:
```cpp
ImGuiIO& io = ImGui::GetIO();
io.Fonts->AddFontFromFileTTF("NotoSansCJKjp-Medium.otf", 20.0f, NULL, io.Fonts->GetGlyphRangesJapanese());
```
```cpp
ImGui::Text(u8"こんにちは！テスト %d", 123);
if (ImGui::Button(u8"ロード"))
{
    // do stuff
}
ImGui::InputText("string", buf, IM_ARRAYSIZE(buf));
ImGui::SliderFloat("float", &f, 0.0f, 1.0f);
```
Result:
<br>![sample code output](https://raw.githubusercontent.com/wiki/ocornut/imgui/web/v160/code_sample_02_jp.png)
<br>_(settings: Dark style (left), Light style (right) / Font: NotoSansCJKjp-Medium, 20px / Rounding: 5)_

### More

Read [misc/fonts/README.txt](https://github.com/ocornut/imgui/blob/master/misc/fonts/README.txt) for more details.