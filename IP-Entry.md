# IP Entry box
by @adam4813
<br>Displays an entry box to allow the user to enter each octet of an IP address

A way to use the entered address is provided by means of a connect button and an IP string builder.

```c++
ImGui::SetNextWindowPosCenter();
ImGui::Begin("IP entry", false, ImGuiWindowFlags_NoResize | ImGuiWindowFlags_NoMove | ImGuiWindowFlags_NoCollapse);

int octets[4] = {123, 123, 123, 123};

float width = ImGui::CalcItemWidth();
ImGui::PushID("IP");
ImGui::AlignFirstTextHeightToWidgets();
ImGui::TextUnformatted("IP");
ImGui::SameLine();
for (int i = 0; i < 4; i++) {
	ImGui::PushItemWidth(width / 4.0f);
	ImGui::PushID(i);
	bool invalid_octet = false;
	if (octets[i] > 255) {
		// Make values over 255 red, and when focus is lost reset it to 255.
		octets[i] = 255;
		invalid_octet = true;
		ImGui::PushStyleColor(ImGuiCol_Text, ImVec4(1.0f, 0.0f, 0.0f, 1.0f));
	}
	if (octets[i] < 0) {
		// Make values below 0 yellow, and when focus is lost reset it to 0.
		octets[i] = 0;
		invalid_octet = true;
		ImGui::PushStyleColor(ImGuiCol_Text, ImVec4(1.0f, 1.0f, 0.0f, 1.0f));
	}
	ImGui::InputInt("##v", &octets[i], 0, 0, ImGuiInputTextFlags_CharsDecimal);
	if (invalid_octet) {
		ImGui::PopStyleColor();
	}
	ImGui::SameLine();
	ImGui::PopID();
	ImGui::PopItemWidth();
}
ImGui::PopID();

// Example action button and way to build the IP string
ImGui::SameLine();
if (ImGui::Button("Connect")) {
	std::stringstream ip;
	ip << octets[0] << "." << octets[1] << "." << octets[2] << "." << octets[3];
}
ImGui::End();
ImGui::SetWindowSize("IP entry", ImVec2(0, 0));
```
![ip_box](https://cloud.githubusercontent.com/assets/3011917/10712482/05d1ef52-7a62-11e5-8d35-9c179abeeec4.png)
