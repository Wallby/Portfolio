---
title: "Fireworks Nuts and Bolts"
subtitle: "Libraries called nuts and bolts because they are for putting together an engine"
tools: [
  "CMake",
  "Batch",
  "Bourne shell",
  "ChromeOS",
  "Git",
  "MinGW"
]
description: "This is my first real project I used CMake with. I took some inspiration from [*-mini](../asterisk_mini). All libraries are written in C-linkeable C++, for which I made up the extensions `.h.hpp` and `.c.cpp`."
download: "https://gitlab.com/fireworks-nuts-and-bolts"
poster: "poster.jpg"
date: 2024-01-01
draft: false
---

<!-- NOTE: "date:" is not accurate -->
The extensions `.h.hpp` and `.c.cpp` I chose because the compilers I used (MSVC and MinGW on Windows, and GCC on ChromeOS) pick a language automatically based on the extension, hence it ends with `.hpp` and `.cpp`.

Currently what works is audio using portaudio and a window with DirectX 11 rendering.