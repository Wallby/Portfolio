---
title: "Sound modeling"
subtitle: "Modeling sound in Supercollider from a reference"
tools: [
  "Supercollider",
  "Audacity"
]
description: "I've often heard of visual artists at [IGAD](https://www.nhtv.nl/ENG/bachelors/creative-media-and-game-technologies/startpage.html) being told by their teacher to gather references. I thought of trying something similar with sound while following a Supercollider course."
trailer: ["whistle.mp4"]
contributions: [
  "Sound programming in Supercollider",
  "Spectrum analysis using Audacity"
]
date: 2022-01-01
draft: false
---

<!-- NOTE: "date:" is not accurate -->

## Spectrum analysis

I used two main ways of analysing the reference, visual spectograms shown in the video, and also the following spectrum plot feature of Audacity..

<div class="row">
<div class="12u">
<img style="width: 100%;max-width: 500px;" src="/img/personal_project/sound_modeling/spectrum_plot.jpg">
</div>
</div>

## Sound programming

The sound is generated using `VarSaw`, which can clearly be seen in the spectogram. The frequency of the `VarSaw` takes an `LFNoise0` as input to not gradually modify the frequency but do so at clear intervals. The output of the `VarSaw` I assigned to a variable called pressure, as this is what I thought to be trying to model, the pressure that changes at a clear interval due to the flute ball "cycling".

Then there is a `SinOsc` for the volume, for which I chose a sine to model the fluctuation of breathing into the whistle. This takes an `LFNoise0` to also have some clear cut frequency changing, which I think was to immitate that every cycle of the whistle ball would probably keep the same pressure, thus changes are more likely to happen clear cut. I also modified the volume with some of the pressure (the var saw), to let that have an effect on loudness too.

For the tone I used a `SinOsc` which directly uses the pressure as input to lerp between min and max freqeuency. The min and max frequency I read from the spectogram shown in the video.

As background/ambient noise there I used `PinkNoise` multiplied by a `SinOsc` which I image is to blend it with the noise that is there as all sound blends together as the waves travel through the same air.

I used mouse input on the X axis to control the exact frequency range, and mouse input on the Y axis to control a lerp between the air and the tone. I moved the mouse around to try to find a nice balance and by printing the values to the console I then copied and hardcoded them to select ones I liked.

This project was mostly a fun experiment, and I make no claims about the objective accuracy of it. It was mostly trying to take a visual-art like "feeling" approach, but an informed one where possible (hence also the reference).