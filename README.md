# Practice-Barebones-Image-Editor
A starting project in developing or integrating a raster and/or vector graphics editing program.

## Motivation
I face an issue when using illustration software like Photoshop, Clip Studio Paint, Krita, etc: the brush engine never seems to fully utilize the full capacity of my systems' hardware. I am exploring how hardware acceleration can be integrated into brush engines and image manipulation software. When using different brushes and using different settings in Clip Studio Paint, I find that when doing painting work on large canvases (e.g: A1 canvas size @ 300DPI), many textured or custom brushes may lag. Even the default G-Pen at large brush sizes (upwards of 1000px) often tend to lag. This occurs regardless when working on raster or vector layers.

I have no formal citations to refer to the current performance metrics of other programs, and this project is based purely on my own experience. I attempted to establish benchmarks, but I realized that it might be outside the scope of what I intend on learning. This is primarily an exercise in learning. So, I will be transparent and disclaim: any performance improvements or benefits found are entirely anecdotal. 
Granted that I have a difficult time with modern illustration software.

## Learning Goals
- LG1: What libraries/integrations currently exist to create an image manipulation program?
- LG2: How do I create a simple blank canvas program that allows me to "draw" on it?
- LG3: How do I reduce or refactor dependencies to optimize performance?
- LG4: What integrations for hardware acceleration exist that might be useful for this project?

## Milestones
1. Make a launchable program that opens a blank canvas that I can draw on.
2. Figure out what rendering engine the program uses, and determine which rendering engine might be best for hardware acceleration.
   - Part of this might be creating a way to switch between rendering engines, to compare performance.
3. Implement graphics tablet driver and pen pressure.
4. Begin scaffolding a brush engine and implement adjustable brush tips.
   - Some initial settings that come to mind: texture, brush size, opacity, mixing, etc.
5. Validate hardware acceleration.

## Deliverables
The final deliverable project should be as simple as a program that opens up to a plain white background (a blank canvas) that you can "draw" on, either using a mouse and cursor, or a graphics tablet.
It should be able to utilize graphics tablet drivers and GPU hardware acceleration, or multi-thread performance.

## Process
### Initial
I begin by considering cross-platform compatibility. I use multiple devices that utilize different graphics architectures and even different CPU architectures. I want to be able to test performance across my Intel x86/Nvidia and Apple ARM64 machines.
Since most development will be done on my x86 machine, I'll focus on that for now, with plans to investigate ARM64 integrations in the future.
If using GPU acceleration, I need to determine what it is I want to render using the GPU. I think both accelerating the canvas viewport and also calculating the brush input data are both good ways to utilize the GPU.
