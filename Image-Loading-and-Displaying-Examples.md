## Index

- [TL;DR;](#tl-dr) 
- [About filenames](#about-filenames)
- [About ImTextureId](#about-imtextureid)
- [Example for OpenGL users](#Example-for-OpenGL-users)
- [Example for DirectX9 users](#Example-for-DirectX9-users)
- [Example for DirectX11 users](#Example-for-DirectX11-users)
- [Example for DirectX12 users](#Example-for-DirectX12-users)
- [More: About Texture Coordinates](#About-texture-coordinates)

## TL;DR;

Loading an image file into a GPU texture is outside of the scope of Dear ImGui and has more to do with your Graphics API. Because this is such a recurring issue for Dear ImGui users, we are providing a guide here.

We will load this image: (Right-click to save as MyImage01.jpg, 20,123 bytes)

![MyPhoto01](https://raw.githubusercontent.com/wiki/ocornut/imgui/tutorials/MyImage01.jpg)

This is generally done in two steps:

- Load image from the disk into RAM. In this example, we'll decompress the image into RGBA a image. You may use helper librairies such as [stb_image.h](https://github.com/nothings/stb/blob/master/stb_image.h) to do this.
- Load the raw decompressed RGBA image from RAM into a GPU texture. You'll want to use dedicated functions of your graphics API (e.g. OpenGL, DirectX11) to do this.

Once you have an image in GPU texture memory, you can use functions such as `ImGui::Image()` to request Dear ImGui to create a draw command that your Dear ImGui rendering back-end will turn into a draw call.

(Note: Large games and applications are likely to be using texture formats that are compressed on the GPU or more advanced techniques that are outside of the scope of this article. Generally, if you are reading this you shouldn't need to worry or care about that.)

##### [Return to Index](#index)

## About filenames

**Please note that many new C/C++ users have issues with their files _because the filename they provide is wrong_.**

Two things to watch for:
- Make sure your IDE/debugger settings starts your executable from the right working directory. In Visual Studio you can change your working directory in project `Properties > General > Debugging > Working Directory`. People assume that their execution will start from the root folder of the project, where by default it oftens start from the folder where object or executable files are stored.
```cpp
filename = "MyImage01.jpg"    // Relative filename depends on your Working Directory when running your program!
```
- In C/C++ and most programming languages if you want to use a backslash `\` within a string literal, you need to write it double backslash `\\`. At it happens, Windows uses backslashes as a path separator, so be mindful.
```cpp
filename = "C:\MyFiles\MyImage01.jpg"         // This is INCORRECT!!
filename = "C:\\MyFiles\\MyImage01.jpg"       // This is CORRECT
```
In some situations, you may also use `/` path separator under Windows.

##### [Return to Index](#index)

## About ImTextureId

From the FAQ: "How can I display an image? What is ImTextureID, how does it works?"

Short explanation:
- You may use functions such as `ImGui::Image()`, `ImGui::ImageButton()` or lower-level `ImDrawList::AddImage()` to emit draw calls that will use your own textures.
- Actual textures are identified in a way that is up to the user/engine. Those identifiers are stored and passed as a `ImTextureID` value (which is no other than a `void*`).
- Loading image files from the disk and turning them into a texture is not within the scope of Dear ImGui (for a good reason). You can read documentations or tutorials on your graphics API to understand how to upload textures. Onward in this document you'll find examples.

Long explanation:
- Dear ImGui's job is to create "meshes", defined in a renderer-agnostic format made of draw commands and vertices. At the end of the frame those meshes (ImDrawList) will be displayed by your rendering function. They are made up of textured polygons and the code to render them is generally fairly short (a few dozen lines). In the examples/ folder we provide functions for popular graphics API (OpenGL, DirectX, etc.).
- Each rendering function decides on a data type to represent "textures". The concept of what is a "texture" is entirely tied to your underlying engine/graphics API. We carry the information to identify a "texture" in the ImTextureID type. ImTextureID is nothing more that a void*, aka 4/8 bytes worth of data: just enough to store 1 pointer or 1 integer of your choice. Dear ImGui doesn't know or understand what you are storing in ImTextureID, it merely pass ImTextureID values until they reach your rendering function.
- In the examples/ bindings, for each graphics API binding we decided on a type that is likely to be a good representation for specifying an image from the end-user perspective. This is what the _examples_ rendering functions are using:
```
OpenGL:    ImTextureID = GLuint                       (see ImGui_ImplOpenGL3_RenderDrawData() in imgui_impl_opengl3.cpp)
DirectX9:  ImTextureID = LPDIRECT3DTEXTURE9           (see ImGui_ImplDX9_RenderDrawData()     in imgui_impl_dx9.cpp)
DirectX11: ImTextureID = ID3D11ShaderResourceView*    (see ImGui_ImplDX11_RenderDrawData()    in imgui_impl_dx11.cpp)
DirectX12: ImTextureID = D3D12_GPU_DESCRIPTOR_HANDLE  (see ImGui_ImplDX12_RenderDrawData()    in imgui_impl_dx12.cpp)
```
For example, in the OpenGL example binding we store raw OpenGL texture identifier (GLuint) inside ImTextureID. Whereas in the DirectX11 example binding we store a pointer to ID3D11ShaderResourceView inside ImTextureID, which is a higher-level structure tying together both the texture and information about its format and how to read it.
- If you have a custom engine built over e.g. OpenGL, instead of passing GLuint around you may decide to use a high-level data type to carry information about the texture as well as how to display it (shaders, etc.). The decision of what to use as ImTextureID can always be made better knowing how your codebase is designed. If your engine has high-level data types for "textures" and "material" then you may want to use them. If you are starting with OpenGL or DirectX or Vulkan and haven't built much of a rendering engine over them, keeping the default ImTextureID representation suggested by the example bindings is probably the best choice. (Advanced users may also decide to keep a low-level type in ImTextureID, and use ImDrawList callback and pass information to their renderer)
User code may do:
```cpp
// Cast our texture type to ImTextureID / void*
MyTexture* texture = g_CoffeeTableTexture;
ImGui::Image((void*)texture, ImVec2(texture->Width, texture->Height));
```
The renderer function called after ImGui::Render() will receive that same value that the user code passed:
```cpp
// Cast ImTextureID / void* stored in the draw command as our texture type
MyTexture* texture = (MyTexture*)pcmd->TextureId;
MyEngineBindTexture2D(texture);
```
Once you understand this design you can begin understand that loading image files and turning them into displayable textures is not within the scope of Dear ImGui. This is by design and is actually a good thing, because it means your code has full control over your data types and how you display them. In reality, the concept of what constitute a "texture" is largely open-ended, and Dear ImGui doesn't want to narrow that concept. If you want to display an image file (e.g. PNG file) into the screen, please refer to tutorials above.

Finally, you may call `ImGui::ShowMetricsWindow()` to explore/visualize/understand how the ImDrawList are generated.

##### [Return to Index](#index)

----

## Example for OpenGL users

We will here use [stb_image.h](https://github.com/nothings/stb/blob/master/stb_image.h) to load images from disk.

Add at the top of one of your source file:
```cpp
#define STB_IMAGE_IMPLEMENTATION
#include "stb_image.h"

// Simple helper function to load an image into a OpenGL texture with common settings
bool LoadTextureFromFile(const char* filename, GLuint* out_texture, int* out_width, int* out_height)
{
    // Load from file
    int image_width = 0;
    int image_height = 0;
    unsigned char* image_data = stbi_load(filename, &image_width, &image_height, NULL, 4);
    if (image_data == NULL)
        return false;

    // Create a OpenGL texture identifier
    GLuint image_texture;
    glGenTextures(1, &image_texture);
    glBindTexture(GL_TEXTURE_2D, image_texture);

    // Setup filtering parameters for display
    glTexParameteri(GL_TEXTURE_2D, GL_TEXTURE_MIN_FILTER, GL_LINEAR);
    glTexParameteri(GL_TEXTURE_2D, GL_TEXTURE_MAG_FILTER, GL_LINEAR);
    glTexParameteri(GL_TEXTURE_2D, GL_TEXTURE_WRAP_S, GL_CLAMP_TO_EDGE); // This is required on WebGL for non power-of-two textures
    glTexParameteri(GL_TEXTURE_2D, GL_TEXTURE_WRAP_T, GL_CLAMP_TO_EDGE); // Same

    // Upload pixels into texture
#if defined(GL_UNPACK_ROW_LENGTH) && !defined(__EMSCRIPTEN__)
    glPixelStorei(GL_UNPACK_ROW_LENGTH, 0);
#endif
    glTexImage2D(GL_TEXTURE_2D, 0, GL_RGBA, image_width, image_height, 0, GL_RGBA, GL_UNSIGNED_BYTE, image_data);
    stbi_image_free(image_data);

    *out_texture = image_texture;
    *out_width = image_width;
    *out_height = image_height;

    return true;
}
```

Load our texture after initializing OpenGL loader (for example after `glewInit()`):
```cpp
int my_image_width = 0;
int my_image_height = 0;
GLuint my_image_texture = 0;
bool ret = LoadTextureFromFile("../../MyImage01.jpg", &my_image_texture, &my_image_width, &my_image_height);
IM_ASSERT(ret);
```

In the snippet of code above, we added an assert `IM_ASSERT(ret)` to check if the image file was loaded correctly. You may also use your Debugger and confirm that `my_image_texture` is not zero and that `my_image_width` `my_image_width` are correct.

Now that we have an OpenGL texture and its dimensions, we can display it in our main loop:
```cpp
ImGui::Begin("OpenGL Texture Text");
ImGui::Text("pointer = %p", my_image_texture);
ImGui::Text("size = %d x %d", my_image_width, my_image_height);
ImGui::Image((void*)(intptr_t)my_image_texture, ImVec2(my_image_width, my_image_height));
ImGui::End();
```

![image](https://user-images.githubusercontent.com/8225057/65344387-dfc21180-dbd7-11e9-9478-627403721435.png)

##### [Return to Index](#index)

----

## Example for DirectX9 users

Unlike the majority of modern graphics API, DirectX9 include helper functions to load image files from disk. We are going to use them here, instead of using `stb_image.h`.

Add at the top of one of your source file:
```cpp
#include <D3dx9tex.h>
#pragma comment(lib, "D3dx9")

// Simple helper function to load an image into a DX9 texture with common settings
bool LoadTextureFromFile(const char* filename, PDIRECT3DTEXTURE9* out_texture, int* out_width, int* out_height)
{
    // Load texture from disk
    PDIRECT3DTEXTURE9 texture;
    HRESULT hr = D3DXCreateTextureFromFileA(g_pd3dDevice, filename, &texture);
    if (hr != S_OK)
        return false;

    // Retrieve description of the texture surface so we can access its size
    D3DSURFACE_DESC my_image_desc;
    texture->GetLevelDesc(0, &my_image_desc);
    *out_texture = texture;
    *out_width = (int)my_image_desc.Width;
    *out_height = (int)my_image_desc.Height;
    return true;
}
```

At initialization time, load our texture:
```cpp
int my_image_width = 0;
int my_image_height = 0;
PDIRECT3DTEXTURE9 my_texture = NULL;
bool ret = LoadTextureFromFile("../../MyImage01.jpg", &my_texture, &my_image_width, &my_image_height);
IM_ASSERT(ret);
```

Now that we have an DirectX9 texture and its dimensions, we can display it in our main loop:
```cpp
ImGui::Begin("DirectX9 Texture Test");
ImGui::Text("pointer = %p", my_texture);
ImGui::Text("size = %d x %d", my_image_width, my_image_height);
ImGui::Image((void*)my_texture, ImVec2(my_image_width, my_image_height));
ImGui::End();
```

![image](https://user-images.githubusercontent.com/8225057/65344041-dedcb000-dbd6-11e9-8a52-120673e8e85f.png)

##### [Return to Index](#index)

----

## Example for DirectX11 users

Add at the top of one of your source file:
```cpp
#define STB_IMAGE_IMPLEMENTATION
#include "stb_image.h"

// Simple helper function to load an image into a DX11 texture with common settings
bool LoadTextureFromFile(const char* filename, ID3D11ShaderResourceView** out_srv, int* out_width, int* out_height)
{
    // Load from disk into a raw RGBA buffer
    int image_width = 0;
    int image_height = 0;
    unsigned char* image_data = stbi_load(filename, &image_width, &image_height, NULL, 4);
    if (image_data == NULL)
        return false;

    // Create texture
    D3D11_TEXTURE2D_DESC desc;
    ZeroMemory(&desc, sizeof(desc));
    desc.Width = image_width;
    desc.Height = image_height;
    desc.MipLevels = 1;
    desc.ArraySize = 1;
    desc.Format = DXGI_FORMAT_R8G8B8A8_UNORM;
    desc.SampleDesc.Count = 1;
    desc.Usage = D3D11_USAGE_DEFAULT;
    desc.BindFlags = D3D11_BIND_SHADER_RESOURCE;
    desc.CPUAccessFlags = 0;

    ID3D11Texture2D *pTexture = NULL;
    D3D11_SUBRESOURCE_DATA subResource;
    subResource.pSysMem = image_data;
    subResource.SysMemPitch = desc.Width * 4;
    subResource.SysMemSlicePitch = 0;
    g_pd3dDevice->CreateTexture2D(&desc, &subResource, &pTexture);

    // Create texture view
    D3D11_SHADER_RESOURCE_VIEW_DESC srvDesc;
    ZeroMemory(&srvDesc, sizeof(srvDesc));
    srvDesc.Format = DXGI_FORMAT_R8G8B8A8_UNORM;
    srvDesc.ViewDimension = D3D11_SRV_DIMENSION_TEXTURE2D;
    srvDesc.Texture2D.MipLevels = desc.MipLevels;
    srvDesc.Texture2D.MostDetailedMip = 0;
    g_pd3dDevice->CreateShaderResourceView(pTexture, &srvDesc, out_srv);
    pTexture->Release();

    *out_width = image_width;
    *out_height = image_height;
    stbi_image_free(image_data);

    return true;
}
```

At initialization time, load our texture:
```cpp
int my_image_width = 0;
int my_image_height = 0;
ID3D11ShaderResourceView* my_texture = NULL;
bool ret = LoadTextureFromFile("../../MyImage01.jpg", &my_texture, &my_image_width, &my_image_height);
IM_ASSERT(ret);
```

Now that we have an DirectX11 texture and its dimensions, we can display it in our main loop:
```cpp
ImGui::Begin("DirectX11 Texture Test");
ImGui::Text("pointer = %p", my_texture);
ImGui::Text("size = %d x %d", my_image_width, my_image_height);
ImGui::Image((void*)my_texture, ImVec2(my_image_width, my_image_height));
ImGui::End();
```

![image](https://user-images.githubusercontent.com/8225057/65343598-a38db180-dbd5-11e9-8776-80dfa4a7f3c6.png)

##### [Return to Index](#index)

----

## Example for DirectX12 users

It should be noted that the DirectX12 API is substantially more complex than previous iterations, and assumes that you will be writing your own code to manage various things such as resource allocation. As such, it's a lot harder to provide a "one size fits all" example than with some APIs, and in all probability the code below will need modification to work with any existing engine code. It should however work if inserted into the Dear ImGui DirectX12 example project, with the caveat that the `CreateDeviceD3D()` function will need to be modified slightly to allocate two descriptors in the SRV resource descriptor heap as follows:

```cpp
{
    D3D12_DESCRIPTOR_HEAP_DESC desc = {};
    desc.Type = D3D12_DESCRIPTOR_HEAP_TYPE_CBV_SRV_UAV;
    desc.NumDescriptors = 2; // <-- Set this value to 2 (the first descriptor is used for the built-in font texture, the second for our new texture)
    desc.Flags = D3D12_DESCRIPTOR_HEAP_FLAG_SHADER_VISIBLE;
    if (g_pd3dDevice->CreateDescriptorHeap(&desc, IID_PPV_ARGS(&g_pd3dSrvDescHeap)) != S_OK)
        return false;
}
```

If you want to use this code to load more than one texture (and don't have your own mechanism for allocating descriptors), then you will need to increase `NumDescriptors` accordingly and also increment `descriptor_index` for each texture loaded.

The actual implementation itself is as follows - firstly, at the top of one of your source files add:
```cpp
#define STB_IMAGE_IMPLEMENTATION
#include "stb_image.h"

// Simple helper function to load an image into a DX12 texture with common settings
// Returns true on success, with the SRV CPU handle having an SRV for the newly-created texture placed in it (srv_cpu_handle must be a handle in a valid descriptor heap)
bool LoadTextureFromFile(const char* filename, ID3D12Device* d3d_device, D3D12_CPU_DESCRIPTOR_HANDLE srv_cpu_handle, ID3D12Resource** out_tex_resource, int* out_width, int* out_height)
{
    // Load from disk into a raw RGBA buffer
    int image_width = 0;
    int image_height = 0;
    unsigned char* image_data = stbi_load(filename, &image_width, &image_height, NULL, 4);
    if (image_data == NULL)
        return false;

    // Create texture resource
    D3D12_HEAP_PROPERTIES props;
    memset(&props, 0, sizeof(D3D12_HEAP_PROPERTIES));
    props.Type = D3D12_HEAP_TYPE_DEFAULT;
    props.CPUPageProperty = D3D12_CPU_PAGE_PROPERTY_UNKNOWN;
    props.MemoryPoolPreference = D3D12_MEMORY_POOL_UNKNOWN;

    D3D12_RESOURCE_DESC desc;
    ZeroMemory(&desc, sizeof(desc));
    desc.Dimension = D3D12_RESOURCE_DIMENSION_TEXTURE2D;
    desc.Alignment = 0;
    desc.Width = image_width;
    desc.Height = image_height;
    desc.DepthOrArraySize = 1;
    desc.MipLevels = 1;
    desc.Format = DXGI_FORMAT_R8G8B8A8_UNORM;
    desc.SampleDesc.Count = 1;
    desc.SampleDesc.Quality = 0;
    desc.Layout = D3D12_TEXTURE_LAYOUT_UNKNOWN;
    desc.Flags = D3D12_RESOURCE_FLAG_NONE;

    ID3D12Resource* pTexture = NULL;
    d3d_device->CreateCommittedResource(&props, D3D12_HEAP_FLAG_NONE, &desc,
        D3D12_RESOURCE_STATE_COPY_DEST, NULL, IID_PPV_ARGS(&pTexture));

    // Create a temporary upload resource to move the data in
    UINT uploadPitch = (image_width * 4 + D3D12_TEXTURE_DATA_PITCH_ALIGNMENT - 1u) & ~(D3D12_TEXTURE_DATA_PITCH_ALIGNMENT - 1u);
    UINT uploadSize = image_height * uploadPitch;
    desc.Dimension = D3D12_RESOURCE_DIMENSION_BUFFER;
    desc.Alignment = 0;
    desc.Width = uploadSize;
    desc.Height = 1;
    desc.DepthOrArraySize = 1;
    desc.MipLevels = 1;
    desc.Format = DXGI_FORMAT_UNKNOWN;
    desc.SampleDesc.Count = 1;
    desc.SampleDesc.Quality = 0;
    desc.Layout = D3D12_TEXTURE_LAYOUT_ROW_MAJOR;
    desc.Flags = D3D12_RESOURCE_FLAG_NONE;

    props.Type = D3D12_HEAP_TYPE_UPLOAD;
    props.CPUPageProperty = D3D12_CPU_PAGE_PROPERTY_UNKNOWN;
    props.MemoryPoolPreference = D3D12_MEMORY_POOL_UNKNOWN;

    ID3D12Resource* uploadBuffer = NULL;
    HRESULT hr = d3d_device->CreateCommittedResource(&props, D3D12_HEAP_FLAG_NONE, &desc,
        D3D12_RESOURCE_STATE_GENERIC_READ, NULL, IID_PPV_ARGS(&uploadBuffer));
    IM_ASSERT(SUCCEEDED(hr));

    // Write pixels into the upload resource
    void* mapped = NULL;
    D3D12_RANGE range = { 0, uploadSize };
    hr = uploadBuffer->Map(0, &range, &mapped);
    IM_ASSERT(SUCCEEDED(hr));
    for (int y = 0; y < image_height; y++)
        memcpy((void*)((uintptr_t)mapped + y * uploadPitch), image_data + y * image_width * 4, image_width * 4);
    uploadBuffer->Unmap(0, &range);

    // Copy the upload resource content into the real resource
    D3D12_TEXTURE_COPY_LOCATION srcLocation = {};
    srcLocation.pResource = uploadBuffer;
    srcLocation.Type = D3D12_TEXTURE_COPY_TYPE_PLACED_FOOTPRINT;
    srcLocation.PlacedFootprint.Footprint.Format = DXGI_FORMAT_R8G8B8A8_UNORM;
    srcLocation.PlacedFootprint.Footprint.Width = image_width;
    srcLocation.PlacedFootprint.Footprint.Height = image_height;
    srcLocation.PlacedFootprint.Footprint.Depth = 1;
    srcLocation.PlacedFootprint.Footprint.RowPitch = uploadPitch;

    D3D12_TEXTURE_COPY_LOCATION dstLocation = {};
    dstLocation.pResource = pTexture;
    dstLocation.Type = D3D12_TEXTURE_COPY_TYPE_SUBRESOURCE_INDEX;
    dstLocation.SubresourceIndex = 0;

    D3D12_RESOURCE_BARRIER barrier = {};
    barrier.Type = D3D12_RESOURCE_BARRIER_TYPE_TRANSITION;
    barrier.Flags = D3D12_RESOURCE_BARRIER_FLAG_NONE;
    barrier.Transition.pResource = pTexture;
    barrier.Transition.Subresource = D3D12_RESOURCE_BARRIER_ALL_SUBRESOURCES;
    barrier.Transition.StateBefore = D3D12_RESOURCE_STATE_COPY_DEST;
    barrier.Transition.StateAfter = D3D12_RESOURCE_STATE_PIXEL_SHADER_RESOURCE;

    // Create a temporary command queue to do the copy with
    ID3D12Fence* fence = NULL;
    hr = d3d_device->CreateFence(0, D3D12_FENCE_FLAG_NONE, IID_PPV_ARGS(&fence));
    IM_ASSERT(SUCCEEDED(hr));

    HANDLE event = CreateEvent(0, 0, 0, 0);
    IM_ASSERT(event != NULL);

    D3D12_COMMAND_QUEUE_DESC queueDesc = {};
    queueDesc.Type = D3D12_COMMAND_LIST_TYPE_DIRECT;
    queueDesc.Flags = D3D12_COMMAND_QUEUE_FLAG_NONE;
    queueDesc.NodeMask = 1;

    ID3D12CommandQueue* cmdQueue = NULL;
    hr = d3d_device->CreateCommandQueue(&queueDesc, IID_PPV_ARGS(&cmdQueue));
    IM_ASSERT(SUCCEEDED(hr));

    ID3D12CommandAllocator* cmdAlloc = NULL;
    hr = d3d_device->CreateCommandAllocator(D3D12_COMMAND_LIST_TYPE_DIRECT, IID_PPV_ARGS(&cmdAlloc));
    IM_ASSERT(SUCCEEDED(hr));

    ID3D12GraphicsCommandList* cmdList = NULL;
    hr = d3d_device->CreateCommandList(0, D3D12_COMMAND_LIST_TYPE_DIRECT, cmdAlloc, NULL, IID_PPV_ARGS(&cmdList));
    IM_ASSERT(SUCCEEDED(hr));

    cmdList->CopyTextureRegion(&dstLocation, 0, 0, 0, &srcLocation, NULL);
    cmdList->ResourceBarrier(1, &barrier);

    hr = cmdList->Close();
    IM_ASSERT(SUCCEEDED(hr));

    // Execute the copy
    cmdQueue->ExecuteCommandLists(1, (ID3D12CommandList* const*)&cmdList);
    hr = cmdQueue->Signal(fence, 1);
    IM_ASSERT(SUCCEEDED(hr));

    // Wait for everything to complete
    fence->SetEventOnCompletion(1, event);
    WaitForSingleObject(event, INFINITE);

    // Tear down our temporary command queue and release the upload resource
    cmdList->Release();
    cmdAlloc->Release();
    cmdQueue->Release();
    CloseHandle(event);
    fence->Release();
    uploadBuffer->Release();

    // Create a shader resource view for the texture
    D3D12_SHADER_RESOURCE_VIEW_DESC srvDesc;
    ZeroMemory(&srvDesc, sizeof(srvDesc));
    srvDesc.Format = DXGI_FORMAT_R8G8B8A8_UNORM;
    srvDesc.ViewDimension = D3D12_SRV_DIMENSION_TEXTURE2D;
    srvDesc.Texture2D.MipLevels = desc.MipLevels;
    srvDesc.Texture2D.MostDetailedMip = 0;
    srvDesc.Shader4ComponentMapping = D3D12_DEFAULT_SHADER_4_COMPONENT_MAPPING;
    d3d_device->CreateShaderResourceView(pTexture, &srvDesc, srv_cpu_handle);

    // Return results
    *out_tex_resource = pTexture;
    *out_width = image_width;
    *out_height = image_height;
    stbi_image_free(image_data);

    return true;
}
```

Then at initialization time, load our texture:
```cpp
// We need to pass a D3D12_CPU_DESCRIPTOR_HANDLE in ImTextureID, so make sure it will fit
static_assert(sizeof(ImTextureID) >= sizeof(D3D12_CPU_DESCRIPTOR_HANDLE), "D3D12_CPU_DESCRIPTOR_HANDLE is too large to fit in an ImTextureID");

// We presume here that we have our D3D device pointer in g_pd3dDevice

int my_image_width = 0;
int my_image_height = 0;
ID3D12Resource* my_texture = NULL;

// Get CPU/GPU handles for the shader resource view
// Normally your engine will have some sort of allocator for these - here we assume that there's an SRV descriptor heap in
// g_pd3dSrvDescHeap with at least two descriptors allocated, and descriptor 1 is unused
UINT handle_increment = g_pd3dDevice->GetDescriptorHandleIncrementSize(D3D12_DESCRIPTOR_HEAP_TYPE_CBV_SRV_UAV);
int descriptor_index = 1; // The descriptor table index to use (not normally a hard-coded constant, but in this case we'll assume we have slot 1 reserved for us)
D3D12_CPU_DESCRIPTOR_HANDLE my_texture_srv_cpu_handle = g_pd3dSrvDescHeap->GetCPUDescriptorHandleForHeapStart();
my_texture_srv_cpu_handle.ptr += (handle_increment * descriptor_index);
D3D12_GPU_DESCRIPTOR_HANDLE my_texture_srv_gpu_handle = g_pd3dSrvDescHeap->GetGPUDescriptorHandleForHeapStart();
my_texture_srv_gpu_handle.ptr += (handle_increment * descriptor_index);

// Load the texture from a file
bool ret = LoadTextureFromFile("../../MyImage01.jpg", g_pd3dDevice, my_texture_srv_cpu_handle, &my_texture, &my_image_width, &my_image_height);
IM_ASSERT(ret);
```

And finally now that we have an DirectX12 texture and its dimensions, we can display it in our main loop:
```cpp
ImGui::Begin("DirectX12 Texture Test");
ImGui::Text("CPU handle = %p", my_texture_srv_cpu_handle.ptr);
ImGui::Text("GPU handle = %p", my_texture_srv_gpu_handle.ptr);
ImGui::Text("size = %d x %d", my_image_width, my_image_height);
// Note that we pass the GPU SRV handle here, *not* the CPU handle. We're passing the internal pointer value, cast to an ImTextureID
ImGui::Image((ImTextureID)my_texture_srv_gpu_handle.ptr, ImVec2((float)my_image_width, (float)my_image_height));
ImGui::End();
```

![Sample screenshot](https://user-images.githubusercontent.com/47202645/82640130-05ab2480-9c45-11ea-9488-82b8554db638.jpg)

##### [Return to Index](#index)

----

## About Texture Coordinates

See e.g. http://wiki.polycount.com/wiki/Texture_Coordinates

For the purpose of this section we use "Texture Coordinates" and "UV Coordinates" interchangeably.

The `ImGui::Image()` and `ImDrawList::AddImage()` functions allow you to pass "UV coordinates" corresponding to the upper-left and bottom-right portion of the texture you want to display. Using the default values, respectively `(0.0f, 0.0f)` and `(1.0f, 1.0f)` for those coordinates allow you to display the entire underlying texture. UV coordinates are traditionally normalized coordinates, meaning that for each axis, instead of counting a number of texels, we address a location in the texture using a number from 0.0f to 1.0f. So (0.0f, 0.0f) is generally addressing the upper-left section of the texture and (1.0f, 1.0f) is addressing the lower-right corner of the texture.

If you want to display part of a texture, say display a 100x200 rectangle stored from pixel (10,10) to pixel (110,210) out of a 256x256 texture, you will need to calculate the normalized coordinates of those pixels:

```cpp
// Normalized coordinates of pixel (10,10) in a 256x256 texture.
ImVec2 uv0 = ImVec2(10.0f/256.0f, 10.0f/256.0f);

// Normalized coordinates of pixel (110,210) in a 256x256 texture.
ImVec2 uv1 = ImVec2((10.0f+100.0f)/256.0f, (10.0f+200.0f)/256.0f);

ImGui::Text("uv0 = (%f, %f)", uv0.x, uv0.y);
ImGui::Text("uv1 = (%f, %f)", uv1.x, uv1.y);

// Display the 100x200 section starting at (10,10)
ImGui::Image((void*)(intptr_t)my_image_texture, ImVec2(100.0f, 200.0f), uv0, uv1);
```

![Using UV](https://user-images.githubusercontent.com/8225057/79073825-f9988280-7ce8-11ea-8596-1fd495720ffa.png)

You can look up "texture coordinates" from other resources such as your favorite search engine, or graphics tutorials.
Tip: map your UV coordinates to widgets (using `SliderFloat2` or `DragFloat2`) so you can manipulate them in real-time and better understand the meaning of those values.

If you want to display the same image but scaled, keep the same UV coordinates but alter the Size:

```cpp
// Normal size
ImGui::Image((void*)(intptr_t)my_image_texture, ImVec2(my_image_width, my_image_height), ImVec2(0.0f, 0.0f), ImVec2(1.0f, 1.0f));

// Half size, same contents
ImGui::Image((void*)(intptr_t)my_image_texture, ImVec2(my_image_width*0.5f, my_image_height*0.5f), ImVec2(0.0f, 0.0f), ImVec2(1.0f, 1.0f));
```

![Scaled](https://user-images.githubusercontent.com/8225057/79073856-25b40380-7ce9-11ea-91e4-754c3232fb58.png)

##### [Return to Index](#index)
