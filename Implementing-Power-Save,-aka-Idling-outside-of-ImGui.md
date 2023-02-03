### Intro

ImGui applications can consume a lot of CPU, since they update the screen very frequently. In order to reduce the CPU usage, it can be desirable to reduce the FPS when no user interaction is detected, in a controllable manner.

[Various PRs address power save](https://github.com/ocornut/imgui/pulls?q=is%3Apr+is%3Aopen+power), by proposing to modify ImGui.

----

Instead of modifying ImGui, an alternative approach is possible and it is not that difficult. It's motto is to say that this is neither a responsibility of ImGui in itself, nor a responsibility of the backend, but the responsibility of an application "runner" that is developed by the user around the backend.

This approach is summarized below. Of course, you may adapt it to your liking.

### 1. Create a storage for the idling data

First, inside the application state rendering function, let's add a storage for the Idling parameters.

For example:
```cpp
struct FpsIdling
{
    float fpsIdle = 9.f;         // FPS when idling
    bool  enableIdling = true;   // a bool to enable/disable idling
    bool  isIdling = false;      // an output parameter filled by the runner
};

// This is your application/runner state.
// Call it whatever you want, store whatever you want in it!
struct RunnerState
{
    // [...] Lots of other params, probably
    FpsIdling fpsIdling;
}
```

### 2. Update your rendering logic

Somewhere in the code, there ought to be a function that polls events, call `ImGui::NewFrame`, calls your Gui code, etc. It is probably called in a loop until the window is closed.

Let's suppose it is called `RenderLogic`. It could be updated like this:

```cpp
void RenderLogic(RunnerState& ioState)
{
    //[...]

    #ifndef __EMSCRIPTEN__
    // This form of idling will call sleep (and is not adapted for emscripten)
    IdleBySleeping(ioState.fpsIdling);
    #endif

    // Backend specific call to poll incoming events (glfwPollEvents, etc.)
    XXXX_PollEvents();

    #ifdef __EMSCRIPTEN__
    if (ShallIdleThisFrame_Emscripten(ioState.fpsIdling))
        // early exit for emscripten
        return;
    #endif

    // Backend specific calls create a new frame, followed by ImGui::NewFrame()
    XXXX_NewFrame_3D();
    XXXX_NewFrame_Backend();
    ImGui::NewFrame();

    //[...] Rest of the rendering logic
}
```

Then, you can implement idling like this:

```cpp
// Idling for non emscripten, where your app is responsible for the main loop.
// This form of idling will call WaitForEventTimeout(), which may call sleep()
void IdleBySleeping(FpsIdling& ioIdling)
{
    ioIdling.isIdling = false;
    if ((ioIdling.fpsIdle > 0.f) && ioIdling.enableIdling)
    {
        double beforeWait = ClockSeconds();
        double waitTimeout = 1. / (double) params.fpsIdling.fpsIdle;

        // Backend specific call that will wait for an event for a maximum duration of waitTimeout
        // (for example glfwWaitEventsTimeout(timeout_seconds))
        XXXWaitForEventTimeout(waitTimeout);

        double afterWait = Internal::ClockSeconds();
        double waitDuration = (afterWait - beforeWait);
        double waitIdleExpected = 1. / params.fpsIdling.fpsIdle;
        ioIdling.isIdling = (waitDuration > waitIdleExpected * 0.9);
    }
}
```

Here, we assume that ClockSeconds() returns the time measured by a global clock ([example](https://github.com/pthom/hello_imgui/blob/master/src/hello_imgui/internal/clock_seconds.cpp))

### 3. If using emscripten change the approach!

For emscripten, the situation is a bit different: in order to not overload the browser, you are supposed to not call your rendering logic in a loop, but instead to register `RenderLogic`, like so:

```cpp
void emscripten_imgui_main_loop(void* arg) {
    RenderLogic(whereverYouStoreYourAppState);
}

int main() {
    // [...]
    emscripten_set_main_loop_arg(emscripten_imgui_main_loop, NULL, ...);
    // [...]
}
```

You cannot call sleep inside emscripten (which would result in a _busy loop_, flooding the cpu). So instead, you opt for an early exit. Something like this can work:

```cpp
// Logic for idling under emscripten
// This test should be done after calling Impl_PollEvents() since it checks the event queue for incoming events!
bool ShallIdleThisFrame_Emscripten(FpsIdling& ioIdling)
{
    ImGuiContext& g = *GImGui;
    bool hasInputEvent =  ! g.InputEventsQueue.empty();

    if (! ioIdling.enableIdling)
    {
        ioIdling.isIdling = false;
        return false;
    }

    static double lastRefreshTime = 0.;
    double now = Internal::ClockSeconds();

    bool shallIdleThisFrame = false;
    if (hasInputEvent)
    {
        ioIdling.isIdling = false;
        shallIdleThisFrame = false;
    }
    else
    {
        ioIdling.isIdling = true;
        if ((now - lastRefreshTime) < 1. / params.fpsIdling.fpsIdle)
            shallIdleThisFrame = true;
        else
            shallIdleThisFrame = false;
    }

    if (! shallIdleThisFrame)
        lastRefreshTime = now;

    return shallIdleThisFrame;
}
```


