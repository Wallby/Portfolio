---
title: "Mayor"
tools: [
  "Unreal Engine",
  "HacknPlan"
]
description: "The second of a total of three sequential game marmalades (2 week game jams). Mayor is a management game in which the player acts as the mayor of a big city plagued by the mafia and everyday problems. Also see [the third](../halo_hunters). Made for educational purposes whilst following the [IGAD](https://www.nhtv.nl/ENG/bachelors/creative-media-and-game-technologies/startpage.html) course at the NHTV in Breda, Netherlands."
slug: "mayor"
trailer: WXgxsMuIlmc
keywords: "game marmalade Unity"
contributions: [
  "Scrum facilitation (Scrum Master)",
  "Tool creation in Excel",
  "Traffic system",
  ]
date: 2017-10-31T21:28:43-05:00
draft: false
---

# What I learned
In the marmalade before this one I learned about Scrum through lots of research, and trial and error. This was my first experience as a Scrum Master, which in combination with a short deadline and high expectations put a lot of responsibility in my hands. The marmalade after that (this one) allowed me to start over and immediately apply and test my newly found insights.

* __<span style="color:#00ff99">Rapid prototyping</span>__  
To get people working quickly and eliminate dependencies as much as possible I focused heavily on measurable small prototypes (e.g. 5 simple heist scenario designs). This had two key benefits: it occupied every member in the team and created a high burn-down velocity, which kept team members motivated.

* __<span style="color:#00ff99">Facilitating communication</span>__  
During the first marmalade, the only communication channel in-place (other than verbal communication) was a single messaging channel through which pretty much everything was communicated. It quickly became apparent that this wasn't sufficient (especially in a rapidly evolving product like this one). To address this I carefully chose a set of communication channels, each having a strongly defined purpose. By enforcing correct usage of the channels the team quickly picked up on them which significantly improved productivity and structure.

* __<span style="color:#ff6666">Velocity tracking</span>__  
As I did lots of research, I also tried out multiple approaches to tracking velocity. The detail that I found lacking during the first marmalade, I found exceeded in this one. In other terms, the amount of effort I put into tracking sprint metrics did not outweigh its benefits as I only ended up using a minimal amount of the metrics that I collected.

* __<span style="color:#ff6666">Planning poker</span>__  
Like the communication, planning went very poorly during the first marmalade. One of the ills of the first planning poker attempt was that it was done over Skype, which is why I planned an on-site meeting and used physical cards this time round. The team's response was all the same: overwhelmingly lethargic. Even though very little was improved, I eventually learned that the two main causes where the scope of the tasks estimating (often too broad or too detailed) and the lack of [assertiveness](../halo_hunters).

# What I made

## Traffic system
<div class="row">
<p class="6u 12u$(small)">
Because of my responsibility as Scrum Master I allowed myself to work only on aesthetic tasks to not bottleneck the game development. As the city layout I was provided with was far from grid-like, I settled on a node-based system, which made it very flexible. The smooth car movement was achieved using some clever tricks to fake acceleration/deceleration.
</p>
<p class="6u 12u$(small)" style="text-align: center;">
<img style="max-width: 400px;" src="/img/projects/mayor/traffic.gif" width=100%>
</p>
</div>
