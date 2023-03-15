---
title: "Arboreal"
tools: [
  "Unreal Engine",
  "Jira",
  "Excel"
]
description: "Arboreal is a game made at my game development bachelor at [IGAD](https://www.nhtv.nl/ENG/bachelors/creative-media-and-game-technologies/startpage.html) in the third year. I joined as the sole dedicated tester in the last quarter of the year. I spent the first 3 quarters of the first year working on other projects including [Project Sulphur](../project_sulphur)."
download: https://store.steampowered.com/app/881300/Arboreal/
slug: "arboreal"
trailer: ["https://cdn.akamai.steamstatic.com/steam/apps/256721888/movie480.webm"]
keywords: ["game", "windows", "downloadable"]
contributions: [
  "Writing and executing of tests",
  "Reporting problems in Jira",
  "Creating an automated spreadsheet to keep track of problems over time"
]
date: 2017-10-31T21:28:43-05:00
draft: false
---

## Automated spreadsheet

I made an Excel workbook that scanned a spreadsheet exported from Jira and automatically generated metrics from it.

The spreadsheet has 3 builtin worksheets, and to use the spreadsheet exported from Jira it has to be imported as a worksheet first.

<div class="row">
  <div class="12u">
    <figure>
      <img src="/img/project/arboreal/spreadsheet_worksheets.jpg" style="width: 100%;max-width: 30em;">
    </figure>
  </div>
</div>

The overview worksheet looks as follows..
<div class="row">
  <div class="12u">
    <figure>
      <img src="/img/project/arboreal/spreadsheet_overview_worksheet.jpg" style="width: 100%;">
      <figcaption>The overview worksheet as seen when zoomed out</figcaption>
    </figure>
  </div>
</div>

<div class="row">
  <div class="6u 12u$(small)">
    <figure>
      <img src="/img/project/arboreal/spreadsheet_input_and_numbers.jpg" style="width: 100%;max-width: 250px;">
	  <br>
	  <p>"Data Sheet" is the name of the worksheet which is expected to be one that was exported by Jira (i.e. the format of this is assumed).
	  <br>
	  The open rate and close rate are the number of bugs opened/closed per week and the fix rate the number of bugs fixed per day (in hindsight it would have made more sense to measure both per week or both per day).
	  <br>
	  The rating is a number between 0 and 10. The way I implemented this at the time (it was my first time doing Quality Assurance) was as the average of the weekly rating, which is calculated as <code>10 - 10 * Open Bugs / Total Bugs</code>. Because of this implementation the rating automatically became higher as bugs were fixed. I think that it would have made more sense to calculate the weekly rating as <code>10 * Closed Bugs / Open Bugs At Start Of Week</code> so 10 would mean there were (at least) as many bugs closed this week as there were at the start of the week.</p>
    </figure>
  </div>
  <br>
  <div class="6u 12u$(small)">
    <figure>
      <img src="/img/project/arboreal/spreadsheet_totals.jpg" style="width: 100%;max-width: 350px;">
    </figure>
    <br>
    <p>"Totals" here means the performance of the entire team, not any individual team member. In hindsight I think replacing "Total Bugs" here with "Open Bugs" and replacing "Open Bugs" with "Bugs Opened This Week" would make sense. This way ideally the "Open Bugs" would be decreasing even if the "Bugs Opened This Week" is increasing.</p>
  </div>
</div>

<div class="row">
  <div class="6u 12u$(small)">
    <figure>
      <img src="/img/project/arboreal/spreadsheet_individual.jpg" style="width: 100%;max-width: 350px;">
	  <br>
	  <p>The individual section shows metrics per team member to see who are fixing bugs and how fast. In hindsight I think priority might have been a good addition, which was exported by Jira, but I think what I managed to implement was a good start.</p>
    </figure>
  </div>
  <br>
  <div class="6u 12u$(small)">
    <figure>
      <img src="/img/project/arboreal/spreadsheet_leaderboard.jpg" style="width: 100%;max-width: 350px;">
    </figure>
    <br>
    <p>In the last week of the the project I finished an idea I had, namely the leaderboard. I shared an image in Slack, and it was well received by the team. Some people said that if was posted every week it would motivate them. However, due to this being completed in the last week it was too late to actually use it.</p>
  </div>
</div>

The other worksheets contain data used by the overview worksheet.
<div class="row">
  <div class="12u">
    <p>The individual effort worksheet looks as follows..</p>
    <figure>
      <img src="/img/project/arboreal/spreadsheet_individual_effort_worksheet.jpg" style="width: 100%;">
      <figcaption>The individual effort worksheet as seen when zoomed out</figcaption>
    </figure>
    <br>
    <p>This worksheet contains the number of bugs closed and opened per week on the right and a summary on  the left as well as the number of total bugs assigned, which isn't measured per week.</p>
  </div>
</div>
<div class="row">
  <div class="12u">
    <p>The overall effort worksheet looks as follows..</p>
    <figure>
      <img src="/img/project/arboreal/spreadsheet_overall_effort_worksheet.jpg" style="width: 100%;max-width: 600px;">
    </figure>
    <br>
    <p>The fix rate here is the per week fix rate summarized on the overview worksheet.</p>
  </div>
</div>
