## Index

- [About filenames](#about-filenames)
- [Font Loading Example](#font-loading-example)

## About filenames

**Please note that many new C/C++ users have issues their files _because the filename they provide is wrong_.**

Two things to watch for:
- Make sure your IDE/debugger settings starts your executable from the right working directory. In Visual Studio you can change your working directory in project `Properties > General > Debugging > Working Directory`. People assume that their execution will start from the root folder of the project, where by default it oftens start from the folder where object or executable files are stored.
```cpp
// Relative filename depends on your Working Directory when running your program!
io.Fonts->AddFontFromFileTTF("MyImage01.jpg", ...);

// Load from the parent folder of your Working Directory
io.Fonts->AddFontFromFileTTF("../MyImage01.jpg", ...);
```
- In C/C++ and most programming languages if you want to use a backslash `\` within a string literal, you need to write it double backslash `\\`. At it happens, Windows uses backslashes as a path separator, so be mindful.
```cpp
io.Fonts->AddFontFromFileTTF("MyFiles\MyImage01.jpg", ...);   // This is INCORRECT!!
io.Fonts->AddFontFromFileTTF("MyFiles\\MyImage01.jpg", ...);  // This is CORRECT
```
In some situations, you may also use `/` path separator under Windows.

##### [Return to Index](#index)

### Font Loading Example

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

##### [Return to Index](#index)

### More

Read [docs/FONTS.txt](https://github.com/ocornut/imgui/blob/master/docs/FONTS.txt) for more details.
But obviously, don't use a Japanese font, it doesn't look good!