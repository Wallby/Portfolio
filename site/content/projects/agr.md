---
title: "AGR"
tools: [
  "Visual Studio",
  "HacknPlan"
]
description: "A game built on top of a custom engine written in C++ running on both the Windows 10 and PS4 platforms. AGR is a high-speed racer player locally with up to four players. Made for educational purposes whilst following the [IGAD](https://www.nhtv.nl/ENG/bachelors/creative-media-and-game-technologies/startpage.html) course at the NHTV in Breda, Netherlands."
slug: "agr"
trailer: GQLV4ADYe18
keywords: "engine cross-platform PS4 Windows"
contributions: [
  "Shadow mapping",
  "Particle systems and editor",
  "Cube map reflections and skybox",
  ]
date: 2017-10-31T21:28:43-05:00
draft: false
---

# What I learned
During the 2 months that this project lasted, I learned graphics programming and PS4 development through hands-on practical experience. The project started with a team of 6 given 1 month to develop an engine, followed up by a month were the team grew to 20 (including artist, designers and programmers) and were development of the engine continued concurrently to the development of a game.

* __<span style="color:#00ff99">Practical and quick</span>__  
The first month of isolated development meant that the engine hadn't been tested too often. However, with our limited knowledge and manpower we managed to deliver a fully functional and playable game.

* __<span style="color:#00ff99">Cross-platform</span>__  
Maintaining multiple platforms and building an architecture to support was not just challenging, but it also gave me the opportunity to implement graphics techniques twice (on different platforms) which tested my knowledge thoroughly.

* __<span style="color:#ff6666">Scoping, prioritization and QA</span>__  
I was quite over-optimistic in my estimating and the majority of the developers in this team showed the same symptoms. We thought we could do far more than we actually could. As a result some features never (fully) made it into the final product.

* __<span style="color:#ff6666">CASE tools</span>__  
Most of the tools we used were those that we had already used before. No dedicated research into better solutions meant that our development process suffered from redundancy.

# What I made

## Shadow mapping
<div class="row">
<p class="6u 12u$(small)">
Something I was determined to learn from the moment this project started was how to implement shadow mapping. I did the implementation for both the DirectX11 and GNMX renderers. The features I worked on are the base shadow mapping, PCF, and normal offset.
</p>
<p class="6u 12u$(small)" style="text-align: center;">
<img style="max-width: 500px;" src="/img/projects/agr/shadows.gif" width=100%>
</p>
</div>

## Particle editor
<div class="row">
<p class="6u 12u$(small)" style="text-align: center;">
<img style="max-width: 600px;" src="/img/projects/agr/spline_editor.gif" width=100%>
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
<img style="max-width: 600px;" src="/img/projects/agr/exhaust.gif" width=100%>
</p>
</div>
<div class="row">
<p class="6u 12u$(small)" style="text-align: center;">
<img style="max-width: 600px;" src="/img/projects/agr/exhaust_smooth.png" width=100%>
</p>
<p class="6u 12u$(small)">
... and here you can see it in the engine. To accommodate for the car's movement I added parenting and 'weights'.
</p>
</div>
