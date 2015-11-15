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

----

**Tip: use Stride for easily plotting a field in array of structures**<br>
https://github.com/ocornut/imgui/issues/271

Here I've got some code sampling joints of an animation as e.g 60 hz.
And I can plot that directly from the joint structure without copying the data around one more time

```cpp
int stride = skel.getBoneCount() * sizeof(JointTransform);
ImGui::PlotLines("RightFoot y", &all_sampled_joints[skel.getBoneIndex("RightFoot")].translation.y, samples, 0, NULL, FLT_MAX, FLT_MAX, ImVec2(0,0), stride);
ImGui::PlotLines("RightToeBase y", &all_sampled_joints[skel.getBoneIndex("RightToeBase")].translation.y, samples, 0, NULL, FLT_MAX, FLT_MAX, ImVec2(0,0), stride);
ImGui::PlotLines("LeftFoot y", &all_sampled_joints[skel.getBoneIndex("LeftFoot")].translation.y, samples, 0, NULL, FLT_MAX, FLT_MAX, ImVec2(0,0), stride);
ImGui::PlotLines("LeftToeBase y", &all_sampled_joints[skel.getBoneIndex("LeftToeBase")].translation.y, samples, 0, NULL, FLT_MAX, FLT_MAX, ImVec2(0,0), stride);
```

![footsteps](https://cloud.githubusercontent.com/assets/8225057/8634511/66076f8e-27b8-11e5-9964-202bf4305802.PNG)

----

**Tip: use c++11 lambas with Combo/ListBox/Plot functions**

```cpp
void SelectBoneByName(const char* label, int* bone_idx, const Skeleton* skeleton)
{
	ImGui::Combo(label, bone_idx, 
		[](void* data, int idx, const char** out_text) { *out_text = skeleton->GetBoneName(idx); return *out_text != NULL; }, 
	(void*)skeleton, skeleton->GetBoneCount());
}
```

```cpp
ImGui::PlotLines("Sin", [](void*data, int idx) { return sinf(idx*0.2f); }, NULL, 100);
ImGui::PlotLines("Cos", [](void*data, int idx) { return cosf(idx*0.2f); }, NULL, 100);
```

![plot func](https://cloud.githubusercontent.com/assets/8225057/8634531/b3281cd6-27b9-11e5-8bf8-ec9f1c67e866.PNG)

Bit awkward with sample indices to plot an actual math function. Ideally here we could introduce variants of plot that use all floats. Will probably add something. 

Likewise for combo boxes, don't copy data around creating list of strings! Use a function to retrieve your data from whatever format it is naturally. The whole plot API is a little awkward and could be reworked along with adding some form of iterator scheme for sparse combo / list-box.
