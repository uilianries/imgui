# Introduction

Vulkan is a modern low level graphics api. With vulkan there are changes that is different from OpenGL and DirectX.

This wiki page is inspired by the article from [François Guthmann](https://frguthmann.github.io/posts/vulkan_imgui/)

This is no way a Vulkan tutorial. To get an idea of the Vulkan API please follow the [vulkan-tutorial](https://vulkan-tutorial.com/)

Note: I am using Vulkan-HPP headers, but you can certainly use the vulkan.h headers.

# Implementation

## Dear ImGui Header Files

* `imconfig.h`
* `imgui.h`
* `imgui_internal.h`
* `imstb_rectpack.h`
* `imstb_textedit.h`
* `imstb_truetype.h`

## Dear ImGui Source Files

The source files you're going to need are:

* `imgui.cpp`
* `imgui_demo.cpp`
* `imgui_draw.cpp`
* `imgui_tables.cpp`
* `imgui_widgets.cpp`

## Vulkan Components that are needed for Dear ImGui
- `VkInstance`
- `VkPhysicalDevice`
- `VkDevice`
- `VkQueueFamily`
- `VkQueue`
- `VkDescriptorPool`
- `VkCommandPool`
- `VkCommandBuffer`
- `VkRenderPass`
- `VkFramebuffer`

## Initialize

First we need to initialize Vulkan. You should already have done so if you're following the [vulkan-tutorial](https://vulkan-tutorial.com/). After getting Vulkan running, we can start an Dear ImGui context. It's recommended to create a seperate `VkDescriptorPool`, `VkRenderPass`, `VkCommandBuffer`, and `VkFramebuffer`. 

```c++
ImGui::CreateContext();
ImGuiIO& io = ImGui::GetIO(); (void)io;
ImGui_Impl{platform}_InitForVulkan(window, true);
```

After starting its context, we give Dear ImGui some of the application Vulkan bindings through an `ImGui_ImplVulkan_InitInfo` struct. We then call `ImGui_ImplVulkan_Init()` passing in a pointer to the `ImGui_ImplVulkan_InitInfo` and a `VkRenderPass`. This will initalize Vulkan for Dear ImGui. 

We then upload font textures to the GPU.

```c++
// Allocate a command buffer

// Record our command buffer
cb.begin({vk::CommandBufferUsageFlagBits::eOneTimeSubmit});
	ImGui_ImplVulkan_CreateFontsTexture(cb);
cb.end();

// Submit to the GPU
vk::SubmitInfo si;
si.commandBufferCount = cb.size();
si.pCommandBuffers = cb.data();
vk::Result res = device->getGraphicsQueue().submit(1, &si, {});
device->getGraphicsQueue().waitIdle(); // Wait for cb is complete
```

### Begin Frame
We need to call the following every frame.

```c++
ImGui_ImplVulkan_NewFrame();
ImGui_ImplGlfw_NewFrame();
ImGui::NewFrame();
```

### Ending Frame
When we end the frame, we want to build the model so we can render this to the screen.
```c++
ImGuiIO& io = ImGui::GetIO();
ImGui::Render();
if (io.ConfigFlags & ImGuiConfigFlags_ViewportsEnable){
	ImGui::UpdatePlatformWindows();
	ImGui::RenderPlatformWindowsDefault();
}
```

### Render
Once we have the model we can finally submit the draw call.
```c++
vk::ClearValue clearValue;
clearValue.color = vk::ClearColorValue(std::array<float, 4>({0.0f, 0.0f, 0.0f, 1.0f}));
cb.begin({vk::CommandBufferUsageFlags()});
	cb.beginRenderPass({
		imguiRenderPass, 
		imguiFramebuffers[swapchainCurrentImage], 
		{{0,0}, swapchainExtent}, 
		1, &clearValue
	}, vk::SubpassContents::eInline);
	ImGui_ImplVulkan_RenderDrawData(ImGui::GetDrawData(), cb);
	cb.endRenderPass();
cb.end();

vk::SubmitInfo si;
si.commandBufferCount = 1;
si.pCommandBuffers = &cb;
graphicsQueue->submit(si);
```

### Resize

When the window viewport resizes, we must create a new `VkFramebuffer` and `VkRenderPass`

### Clean up

At the end of the application life-cycle, we must destroy our ImGui context. 

* `ImGui_ImplVulkan_Shutdown()`
* `ImGui_ImplGlfw_Shutdown()`
* `ImGui::DestroyContext()`

## Using the API
In our application life cycle we should have
```c++
while(true){
    updateWindow();
    
    rendererBeginFrame(); // Acquire images
    imguiBeginFrame();
    ImGui::ShowDemoWindow(); // Issue ImGui commands
    imguiEndFrame();

    imguiRender(); // Submit Command buffers to screen

    rendererPresent(); // Present to the screen
}
```