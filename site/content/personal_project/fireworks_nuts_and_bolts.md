---
title: "Fireworks Nuts and Bolts"
subtitle: "Libraries called nuts and bolts because they are parts of what would be a game engine"
tools: [
  "CMake",
  "Batch",
  "Bourne shell",
  "DirectX 11",
  "DirectX 12",
  "Vulkan",
  "Portaudio"
]
description: "This is my first real project I used CMake with. I took some inspiration from [*-mini](../asterisk_mini)."
download: "https://gitlab.com/fireworks-nuts-and-bolts"
trailer: ["2024_footage.mp4"]
contributions: [
    "Build pipeline using CMake",
    "Release pipeline using shell scripts",
    "Sound and graphics programming"
  ]
date: 2024-01-01
draft: false
---

<!-- NOTE: "date:" is not accurate -->
All libraries are written in C-linkeable C++, for which I made up the extensions `.h.hpp` and `.c.cpp`. The extensions `.h.hpp` and `.c.cpp` I chose because the compilers I used (MSVC and MinGW on Windows, and GCC on ChromeOS) pick a language automatically based on the extension, hence it ends with `.hpp` and `.cpp`.

The project currently consists of..
* Assets, a library for parsing various file formats
* Core, a library containing framework functionality that the other libraries should fill in
* GPU, a library for GPU APIs
* Light, a library for graphics programming
* Reusable, the only library that a release version of another project may use, as all the code from this can (and must) be inlined
* Sound, a library for sound programming
* Testing, a library for writing tests
* Window, a library for sound and graphics
* UI, a library for (graphical) user interfaces

I have implemented audio using portaudio and a Win32 window in the Window project. My XLib window implementation stopped working on ChromeOS (Linux virtual machine), but used to work fine on Linux. I haven't gotten to trying to solve that yet. The Window project actually refers to audio and graphics as two types of windows, visual windows and audible windows.

I have implemented DirectX 11 rendering in the GPU project. I also have a working Vulkan implementation and DirectX12 implementation, but no time yet to properly clean those up to be ready for committing.

The Assets, Core, Light, Sound, Testing and UI projects are work in progress. Of these Core and Testing have progress, the others are not yet started. The Core project should contain resources, time, internationalization, and a rendering state machine. With a rendering patching state machine framework I mean that it allows for specifying patch types and patch moments, and then resources can require patches. For example, an update CPU patch can require a copy resource to GPU patch. A patch moment for that could be before beginning a command buffer for Vulkan. All that then has to be done before beginning the command buffer is apply any patches that can be applied at that moment, and the rest will be automated.

A difference from [*-mini](../asterisk_mini) is that there I copied over reusable code between projects. In this project I used CMake's `configure_file` to automate this, which is mostly what the Reusable project is for. Other than inline code there is also a CMake library in the Reusable project.