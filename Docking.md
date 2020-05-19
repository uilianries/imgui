## Preamble

#### Where to find it?

Docking is currently available in the [docking](https://github.com/ocornut/imgui/tree/docking) branch. This is a well maintained branch and most large teams have been using this branch for a while. It is safe and recommended to use that branch.

#### How can I enable docking?

`ImGui::GetIO().ConfigFlags |= ImGuiConfigFlags_DockingEnable;`

That's pretty much it.
There are 4 additional docked related configuration flags in the io structure which you may toy with.

#### Why is not merged to master?

(Please note that the following paragraphs have been written by a overly cautious person)

Several advanced features, such as tight interaction with native multi-viewports, or the DockBuilder are still expecting api changes. I am also not particularly happy with how some aspects of the code are current implemented, and considering to maybe rewrite all of docking from scratch a third time! 

However, you can benefit from a lot of docking features without being impacted by any of this. **The largest amount of interactions you'll have with the docking system are a user level and not at API level**. By just enabling the config flag above and calling 1-2 functions you can benefit from 90% of Docking features. Even the hypothetical full rewrite of Docking system is not expected to impact most users. API that are most at risk of changing are hidden in `imgui_internal.h` for this reason, and even so, if they do change, we'll make reasonable effort to document the reasoning the update path. 

In addition, Docking will only move forward with feedback from users, so the more people using it, the closer we are to a reach mergeable version. TL;DR; is totally fine to use for most users.

## Usage Guide

Also see our [[Glossary]] about Docking terminology.

#### Docking

- Merge into existing node
- Split existing node

#### Undocking

- Undock a window from a node
- Undock a node from a hierarchy

#### Settings, Persistence model

- Explain how/why the data persist

#### Dockspace

- Explain dockspace (~~ node positioned within an existing window)
- Explain central node

#### Debugging

- Metrics window.
- Enable `IMGUI_DEBUG_LOG_DOCKING()`
