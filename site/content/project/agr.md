---
title: "AGR"
tools: [
  "Visual Studio",
  "HacknPlan"
]
description: "A game built using a custom engine made in the third year of my
game development bachelor at  [IGAD](https://www.nhtv.nl/ENG/bachelors/creative-media-and-game-technologies/startpage.html). The engine was written completely in C++ over a period of 16 weeks and runs
on both Windows and PS4. The game AGR, an anti-grav racer, was made in unison
with the development of the tech. As a graphics programmer I setup the
foundations for cross-platform rendering and implement several effects,
including shadow mapping."
slug: "agr"
#trailer: GQLV4ADYe18 #< This is the official trailer, which doesn't include many of the FX
trailer: qtfIpzz7y7w
keywords: "engine cross-platform PS4 Windows"
contributions: [
  "Shadow mapping in DX11 and GNMX",
  "Particle systems in DX11 and GNMX",
  "Particle system editor with preview",
  "Cube mapped reflections and skybox in DX11 and GNMX",
  ]
date: 2017-10-31T21:28:43-05:00
draft: false
---

## Shadow mapping
<div class="row">
<p class="6u 12u$(small)">
Something I was determined to learn from the moment this project started was how to implement shadow mapping. I did the implementation for both the DirectX11 and GNMX renderers. The features I worked on are the base shadow mapping, PCF, and normal offset.
</p>
<p class="6u 12u$(small)" style="text-align: center;">
<img style="max-width: 500px;" src="/img/project/agr/shadows.gif" width=100%>
</p>
</div>

## Particle editor
<div class="row">
<p class="6u 12u$(small)" style="text-align: center;">
<img style="max-width: 600px;" src="/img/project/agr/spline_editor.gif" width=100%>
</p>
<p class="6u 12u$(small)">
Since the engine and game were developed simultaneously, I created incremental versions of the particle editor. Meanwhile, I changed the particles from physics- to curve-based</a>, and optimized the rendering reducing bandwidth (using the geometry shader) and draw calls (batching).
</p>
</div>
<div class="row">
<p class="6u 12u$(small)">
Here you can see the car exhaust particle system in the editor...
</p>
<p class="6u 12u$(small)" style="text-align: center;">
<img style="max-width: 600px;" src="/img/project/agr/exhaust.gif" width=100%>
</p>
</div>
<div class="row">
<p class="6u 12u$(small)" style="text-align: center;">
<img style="max-width: 600px;" src="/img/project/agr/exhaust_smooth.png" width=100%>
</p>
<p class="6u 12u$(small)">
... and here you can see it in the engine. To accommodate for the car's movement I added parenting and 'weights'.
</p>
</div>
