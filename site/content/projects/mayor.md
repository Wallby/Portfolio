---
title: "Mayor"
tools: [
  "Unreal Engine",
  "HacknPlan"
]
description: "Mayor is a city management game made in the third year of my game development bachelor at  [IGAD](https://www.nhtv.nl/ENG/bachelors/creative-media-and-game-technologies/startpage.html). The game was made from concept to final product in a period of two and a half weeks as part of a so-called game marmalade (i.e. an extended game jam). Another marmalade game is [Halo Hunters](../halo_hunters)."
slug: "mayor"
trailer: WXgxsMuIlmc
keywords: "game marmalade Unity"
contributions: [
  "Project management as Scrum Master",
  "Traffic system in Blueprints",
  "Automation tools made in Excel",
  ]
date: 2017-10-31T21:28:43-05:00
draft: false
---

## Traffic system

Because of my irregular schedule as a result of growing into the role of Scrum Master, I allowed myself to work only on aesthetic tasks to not become a bottleneck for others.

The task I spent most of my non-scrum-master time on was the traffic system, intended to bring some life into the scene.

<!-- TODO: Replace hr solution with actual swapping of column order for mobile -->

<hr>

<div class="row">
<p class="6u 12u$(small)" style="text-align: center;">
<img style="max-width: 300px;" src="/img/projects/mayor/traffic_nodes_in_editor.png" width=100%>
<br>
<i>The traffic node gizmos as seen in the editor</i>
<br>
<img style="max-width: 300px;" src="/img/projects/mayor/traffic_node_inspector.png" width=100%>
<br>
<i>The inspector view on a traffic node actor</i>
</p>
<p class="6u 12u$(small)">
The city layout was not entirely grid-like (though every corner is a right angle). Because of this I settled on a pathing graph system. Each node in the graph knows to which neighboring nodes it is connected (a node is represented as a white sphere in the scene).
</p>
</div>

<hr>

<div class="row">
<p class="6u 12u$(small)">
A central traffic manager is responsible for the spawning, updating, and despawning of the cars.
</p>
<p class="6u 12u$(small)" style="text-align: center;">
<img style="max-width: 300px;" src="/img/projects/mayor/traffic_manager.png" width=100%>
<br>
<i>The inspector view on the traffic manager actor</i>
</p>
</div>

<hr>

<div class="row">
<p class="6u 12u$(small)" style="text-align: center;">
<img style="max-width: 400px;" src="/img/projects/mayor/traffic.gif" width=100%>
</p>
<p class="6u 12u$(small)">
The car actors themselves are actually all on the center of the street, but the model itself is offset to one side (kudos to the artist who inspired this simple and neat solution).
</p>
</div>