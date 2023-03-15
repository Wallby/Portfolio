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
trailer: ["2022_agr_gameplay.mp4"]
keywords: ["tool", "engine", "ps4", "windows"]
contributions: [
  "Shadow mapping in DX11 and GNMX",
  "Particle systems in DX11 and GNMX",
  "Particle system editor with preview",
  "Cube mapped reflections and skybox in DX11 and GNMX",
  ]
date: 2017-10-31T21:28:43-05:00
draft: false
---

<p id="note">NOTE: I fixed some stuff (click <a href=#2022>here</a> to see what) and replaced the shadow camera transform calculation in 2022. The footage above is from 2022. The trailer at the time the project ended at IGAD can be watched <a href=https://www.youtube.com/watch?v=GQLV4ADYe18>here</a> though in this trailer a mixture of footage is used some showing different features working than others.</p>

## Shadow mapping
<div class="row">
<p class="6u 12u$(small)">
Something I was determined to learn from the moment this project started was how to implement shadow mapping. I did the implementation for both the DirectX11 and GNMX renderers. The features I worked on are the base shadow mapping, PCF, and normal offset. Two shadowmaps are rendered, one higher resolution shadowmap for only the player's car and one lower resolution shadowmap with greater coverage for everything but the player's car.
</p>
<div class="6u 12u$(small)">
<img style="width: 100%;max-width: 500px;" src="/img/project/agr/shadows.gif">
</div>
</div>

## Particle editor
<div class="row">
  <div class="6u 12u$(small)">
    <img src="/img/project/agr/spline_editor.gif" style="width: 100%;max-width: 600px;">
  </div>
  <p class="6u 12u$(small)">Since the engine and game were developed simultaneously, I created incremental versions of the particle editor. Meanwhile, I changed the particles from physics- to curve-based</a>, and optimized the rendering reducing bandwidth (using the geometry shader) and draw calls (batching).</p>
</div>
<div class="row">
  <p class="6u 12u$(small)">Here you can see the car exhaust particle system in the editor...</p>
  <div class="6u 12u$(small)">
    <img src="/img/project/agr/exhaust.gif" style="width: 100%;max-width: 600px;">
  </div>
</div>
<div class="row">
  <div class="6u 12u$(small)">
    <img src="/img/project/agr/exhaust_smooth.png" style="width: 100%;max-width: 600px;">
  </div>
  <p class="6u 12u$(small)">... and here you can see it in the engine. To accommodate for the car's movement I added parenting and 'weights'.</p>
</div>

## 2022

In 2022 I removed the broken shadow camera transform calculation algorithm and created one that works. I also fixed some other stuff left broken, such as splitscreen postprocessing and fixed that a shadow was not always fully rendered for another player's car.

<div class="row">
  <div class="6u 12u$(small)">
    <img src="/img/project/agr/2022_shadow_camera_transform_calculation_1.gif" style="width: 100%;max-width: 600px;">
  </div>
  <p class="6u 12u$(small)">The working shadow camera transform calculation algorithm uses the player's camera's forward direction if the player's camera's forward direction is perpendicular to the light direction. The shadowmap for everything but the player's car is shown here at the center right (black and red).</p>
</div>
  <div class="row">
  <p class="6u 12u$(small)">If the player's camera's forward is parallel to the light direction.. the player's camera's up direction is used instead.</p>
  <div class="6u 12u$(small)">
    <img src="/img/project/agr/2022_shadow_camera_transform_calculation_2.gif" style="width: 100%;max-width: 600px;">
  </div>
</div>
<div class="row">
  <div class="6u 12u$(small)">
    <img src="/img/project/agr/2022_splitscreen_car_shadows.jpg" style="width: 100%;max-width: 600px;">
  </div>
  <p class="6u 12u$(small)">The shadow for another player's car is now rendered to the greater coverage shadowmap.</p>
</div>

