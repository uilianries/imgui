## What happened in 2019

Been meaning to give a quick overview of the things that happened in 2019...

Spanning versions 1.67 - 1.75: [we’ve got about 700 lines worth of Changelog](https://github.com/ocornut/imgui/releases): new features, fixes, optimizations, demo improvements. I initially wanted to write a summary of those, but the amount of useful details is too large. I heartfully recommend organizing your work to stay up to date with Dear ImGui.

Removed dozens of renamed or misleading legacy symbols marked obsolete in 1.50 - 1.53 (up to December 2017). Some of those symbols were polluting the namespace and creating unnecessary confusion. The “API Breaking Changes” section of imgui.cpp describe all those changes in details.

Exactly **700 Issues or Pull-Request have been opened in 2019 on GitHub**. Hundreds of other issues have been opened through private channels and paid support. 

With about 19k stars and 3k forks, Dear ImGui appears to be the 9th most starred C++ repository on GitHub ([source](http://gitmostwanted.com/top/stars/?lang=C%2B%2B)). This is a thoroughly meaningless metrics, but hey, it's nice.

## Making the project reliable, sustainable, growing the team

In 2018 I identified that one weakness of Dear ImGui was that I @ocornut was more or less the sole dedicated developer on it. While it enabled consistency and enforcing strong technical and design stance, it has been both a bottleneck and a risk. 
- It is a bottleneck because it is becoming increasingly apparent that Dear ImGui is larger than me and having more people dedicated to its improvement wouldn’t be a luxury. 
- It is a risk to be relying on software mostly carried by a single person while expecting continued improvements. While strongly mitigated by the fact that the project is using a permissive license and is easy to hack, we can still aim to lower that risk.

Some of the work in 2019 has been focused around improving the situation:
- I kept working **transitioning the funding model** from e.g. Patreon and occasional private deals to working directly with more businessesi, toward a more sustainable model allowing us to keep Dear ImGui a permissive free software. This has been a long journey. From the end of 2017 [Blizzard](https://careers.blizzard.com/en-us/openings/engineering/all/all/all/1) have been funding a good portion of my work, I have been working toward extending partnership with others. Companies like [Ubisoft](https://montreal.ubisoft.com/en/ubisoft-sponsors-user-interface-library-for-c-dear-imgui/), [Nvidia](https://developer.nvidia.com/nvidia-omniverse), [Google](https://github.com/google/filament) and dozens of others are now increasingly getting involved. I have closed the Patreon in December 2019 to full mark the transition toward a B2B model.
- Today with extra funding from many partners we are in a capacity to **start getting more people involved with the project**. Earlier in 2019 Adrien [@LaMarche05](https://github.com/LaMarche05) contributed a few months on the automation system, Rokas [@rokups](https://github.com/rokups/) is now spending an increasing amount of time taking variety of tasks off me, and Ben [@ShironekoBen](https://github.com/ShironekoBen) recently joined also lending a hand. As I result you will notice that an increasing amount of contributions in recent releases are marked with new user names, as I've been spending more time working with them. Hopefully we can make those contributions sustainable and even grow them in 2020. If your company uses Dear ImGui, please reach out to help sustain this project! (e-mail: _contact at dearimgui dot org_).
- Working with more people has been forcing me to incrementally adjust my processes and tools. I have been moving things previously scattered into local stashes and hard drive folders into the cloud in public or semi-public sight. We’re currently working on **an upcoming imgui_dev repository** (automation system, regression tests, variety of scripts and helpers’ tools) and hundreds of notes, branches and stashes were or are being moved to online documents or dedicated repositories available to a growing number of developers. Over time the aim is of course to make everything public.
- We worked on an **automation and regression testing framework**. We are now running an increasing suite of low and high-level regression tests and working toward systems to allow users to test their own applications. Those tests are helpful to improve general reliability, to facilitate changes, track performances, increase confidence and onboard new programmers on the project. Complex and features like the Docking system are become less fragile over time thanks to it. The testing framework can run headless (e.g. on a server) or embedded in an app with its own GUI.
- We worked on using automation to capture pictures and video. We intend to use automated systems to generate contents for future documentation and wiki (as a symbolic steppingstone, some of the image appearing in the readme are now generated using automation). 
- We worked on setting up more rigorous **continuous integration systems**. We now build several dozen tests projects on the cloud, covering five platforms, static analysis, variety of compilers and unusual corner cases (configuration defines, etc.).
- Amusing to say as we are still under-documented, but **documentation has been improving**. The [Wiki](https://github.com/ocornut/imgui/wiki) is better, the Readme is better, the [FAQ](https://github.com/ocornut/imgui/blob/master/docs/FAQ.md) is better, we have a [Glossary](https://github.com/ocornut/imgui/wiki/Glossary), some files are better organized, code has more comments, we have a few articles on recurring issues (e.g. [image loading and displaying](https://github.com/ocornut/imgui/wiki/Image-Loading-and-Displaying-Examples)), we have a [Discord server](http://discord.dearimgui.org).

![test_engine](https://user-images.githubusercontent.com/8225057/74144582-4f738000-4bfd-11ea-87a2-7a142f4172fe.png)

![ci](https://user-images.githubusercontent.com/8225057/74144910-ea6c5a00-4bfd-11ea-8243-066229ca7166.PNG)

Preserving the core project values is key. While we are sitting on a project whose scope and expectations grew massively since its inception, we are still focused on performance, compatibility, extensibility, simplicity, leanness. They are all important and I am serious at protecting those values. We’re also dealing with slowly steering a project into its 2.0 incarnation, without breaking too much of people’s codebase. Please bear with us, it means things always take much longer to make. Many interconnected ideas are being tested and waiting for their right moment to be turned into production-quality features. It means maybe some of you feel like Dear ImGui is not moving forward fast enough, and it still is missing many features. We’ll address them over time and with your support. 

## Features and ongoing 2019 work

Some of the large axises of work included:

**Docking and Multi-Viewports**: both in ‘docking’ branch, have received countless fixes and small improvements. Reminder that this branch is kept up to date with master and it is perfectly usable in production - most large users have been on the docking branch, so this is the de-facto main branches for many. Some of the changes are still experimental and intentionally poorly documented, as we still are working with high-end users to improve things toward seamless desktop experience. We are still working out a transition to move those features into master, and the adoption of regression tests was partly motivated by the need to facilitate working in some of the more complex areas of the Docking system.

**DPI**: work has been done at better supporting varying DPI settings. While regular “single viewport, varying-dpi / hi-dpi” support is easy to handle at user-level, what we call “multi-dpi” (= multiple viewports simultaneously scattered over multiple monitors with varying DPI scale) has been particularly tricky to find perfect solutions for and we are still experimenting with tradeoffs. Shamefully I must admit we have neglected to provide a trivial and ready-to-use solution for the simpler case of supporting “single-viewport varying-dpi” because we were too focused on the difficult end of the problem. We should remedy to that soon.

**Keyboard and Gamepad control**s: many user-facing fixes and internal improvements have also happened here. This should be a major axis of work in 2020 (focusing, input dispatching, shortcut) as there is increasing pressure to provide quality keyboard controls for productivity tools.

![Keyboard controls](https://user-images.githubusercontent.com/8225057/74143829-ce67b900-4bfb-11ea-90d9-0de40c944b26.gif)

**Tables**: work has been done on a new Tables API aimed at replacing columns (currently in public testing phase).
This is not an exhaustive list, as mentioned hundreds of changes were done between 1.67 and 1.75 (e.g. 1.67 introduced the tab bar api backported from Docking branch) and many new things are in the work.

![Tables](https://user-images.githubusercontent.com/8225057/71590287-248b0c00-2b28-11ea-8a1a-761f0b55c976.png)

This is by no mean an exhaustive list of things that happened in 2019. Check [releases notes](https://github.com/ocornut/imgui/releases) and active [github issues](https://github.com/ocornut/imgui/issues) for more details.

