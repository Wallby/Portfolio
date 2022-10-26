---
title: "arguments-mini"
tools: [
  "Make"
]
description: "A single .cpp file library written in \"C linkable C++\" (C++ with inline new and delete) for parsing commandline arguments."
slug: "arguments_mini"
poster: "poster.gif"
keywords: ["commandline arguments", "linux", "windows"]
download: "https://github.com/Wallby/arguments-mini"
date: 2022-01-28T16:18:28+01:00
draft: false
---

## [arguments-mini-test](https://github.com/Wallby/arguments-mini-test)

Before release [0.2.1 (patch for beta)](https://github.com/Wallby/arguments-mini/releases/tag/0.2.1-beta) arguments-mini-test ran two tests (one to test if a valid argv did succeed, and another to test if an invalid argv did not succeed).

<div class="row">
  <div class="12u">
    <figure>
      <!-- image-border and no-image-border here as 919px is width of image (i.e. "border-width") -->
      <div id="image-border">
        <img src="/img/project/arguments_mini/arguments_mini_test.png" id="no-image-border" style="width: 100%;max-width: 919px;">
      </div>
      <figcaption style="text-align: center;">Output of argument-mini-test 0.2.1</figcaption>
    </figure>
  </div>
</div>

With release 0.2.1 these tests were removed and I added three tests..
* one for argument parsing
* one for parameterwithvalue parsing
* one for parameterwithoutvalue parsing.

Also.. I added an `andrun` target for make such that running `make andrun` (as was done in the image above) would..
1. assure `arguments-mini-test` on linux/`arguments-mini-test.exe` on windows was up to date
2. run `arguments-mini-test`/`arguments-mini-test.exe`

