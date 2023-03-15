---
title: "Mayor"
tools: [
  "Unreal Engine",
  "HacknPlan",
  "Excel"
]
description: "Mayor is a city management game made in the second year of my game development bachelor at  [IGAD](https://www.nhtv.nl/ENG/bachelors/creative-media-and-game-technologies/startpage.html). The game was made from concept to final product in a period of two and a half weeks as part of a so-called game marmalade (i.e. an extended game jam). Another marmalade game is [Halo Hunters](../halo_hunters)."
slug: "mayor"
trailer: ["youtube","WXgxsMuIlmc"]
keywords: ["game", "game marmalade"]
contributions: [
  "Project management as Scrum Master",
  "Traffic system in Blueprints",
  "Created spreadsheet for calculating working hours",
  ]
date: 2017-10-31T21:28:43-05:00
draft: false
---

## Scrum master

During a workshop I saw someone gathering the available hours of each team member as working/available/unavailable/ICE (available in case of emergency). I created a spreadsheet and requested each team member to fill it in. I added some color for readability and added a summary on the right.

<div class="row">
  <div class="12u">
    <figure>
      <img src="/img/project/mayor/hoursspreadsheet_individual.jpg" style="width: 100%;max-width: 30em;">
    </figure>
  </div>
</div>

On another worksheet I added a summary calculating the total number of hours available.

<div class="row">
  <div class="12u">
    <figure>
      <img src="/img/project/mayor/hoursspreadsheet_total.jpg" style="width: 100%;max-width: 30em;">
    </figure>
  </div>
</div>

In the sprint planning and HacknPlan the metric used was hours, hence this was consistent everywhere

## Traffic system

Because of my irregular schedule as a result of growing into the role of Scrum Master, I allowed myself to work only on aesthetic tasks to not become a bottleneck for others.

The task I spent most of my non-scrum-master time on was the traffic system, intended to bring some life into the scene.

<div class="row">
  <div class="6u 12u$(small)">
    <figure>
      <img src="/img/project/mayor/traffic_nodes_in_editor.png" style="width: 100%;max-width: 300px;">
      <figcaption>The traffic node gizmos as seen in the editor</figcaption>
    </figure>
  </div>
  <br>
  <div class="6u 12u$(small)">
    <figure>
      <img src="/img/project/mayor/traffic_node_inspector.png" style="width: 100%;max-width: 300px;">
      <figcaption>The inspector view on a traffic node actor</figcaption>
    </figure>
    <br>
    <p >The city layout was not entirely grid-like (though every corner is a right angle). Because of this I settled on a pathing graph system. Each node in the graph knows to which neighboring nodes it is connected (a node is represented as a white sphere in the scene).</p>
  </div>
</div>

<div class="row">
  <p class="6u 12u$(small)">A central traffic manager is responsible for the spawning, updating, and despawning of the cars.</p>
  <div class="6u 12u$(small)">
    <figure>
      <img src="/img/project/mayor/traffic_manager.png" style="width: 100%;max-width: 300px;">
      <figcaption>The inspector view on the traffic manager actor</figcaption>
    </figure>
  </div>
</div>

<div class="row">
  <div class="6u 12u$(small)">
    <img src="/img/project/mayor/traffic.gif" style="width: 100%;max-width: 400px;">
  </div>
  <p class="6u 12u$(small)">The car actors themselves are actually all on the center of the street, but the model itself is offset to one side (kudos to the artist who inspired this simple and neat solution).</p>
</div>