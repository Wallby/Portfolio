---
title: "*-mini"
subtitle: "Several \"single file\" libraries I made as a hobby"
tools: [
  "Make",
  "Batch",
  "Bourne shell",
  "Git",
  "Eclipse IDE"
]
description: "Several \"single file\" (i.e. the \"\" because in some cases there are two identically named files, namely one .h and one .c(pp)) libraries, some written in C linkeable C++ (i.e. not requiring linking to the C++ standard library binary), others written in C and one in Makefile. All libraries work on both windows and linux."
download: "https://github.com/Wallby?tab=repositories&q=in%3Aname+-mini&type=&language=&sort="
keywords: ["tool", "library", "linux", "windows", "downloadable"]
poster: "poster.gif"
date: 2022-01-28
draft: false
---
<!-- NOTE: "date:" is not exact, date and month are not checked -->

Current libraries..
* [tcp-mini](https://github.com/Wallby/tcp-mini) (C++ TCP library for running one server to which client(s) can connect, non blocking)
* [arguments-mini](https://github.com/Wallby/arguments-mini) (C++ library for parsing `argc` and `argv` using a format I personally use often)
* [tint-mini](https://github.com/Wallby/tint-mini) (C library for converting between different tint representations)
* [test-mini](https://github.com/Wallby/test-mini) (C library that wraps main, malloc and free to detect memory leaks and also provide macros for running unit tests)
* [array-mini](https://github.com/Wallby/array-mini) (C library for array operations on pointers using elements of any size)
* [check-mini](https://github.com/Wallby/check-mini) (C library for validating variables by calling a validation function that can be derived from the variable's type, the variable's name or specified explicitly)
* [makefile-mini](https://github.com/Wallby/makefile-mini) (makefile library for generating targets I use in all *-mini projects)
* [sharedlibrary-mini](https://github.com/Wallby/sharedlibrary-mini) (library for compile time linking and runtime linking of sharedlibraries (.dll for windows and .so for linux))
* [clock-mini](https://github.com/Wallby/clock-mini) (library for atleast microsecond precise time representation and converting between different time units)
* [lcg-mini](https://github.com/Wallby/lcg-mini) (library for generating psuedorandom numbers from a seed and a variable)

The first library I made was tcp-mini. I had never done socket programming before and nor linux programming (well a bit during my bachelor during a course, but the course supplied the linux things and focussed on opengl things), tcp-mini was my first introduction to both of these.

As I learned and sought answers to questions I added more features, some of which became later libraries (array-mini, check-mini, test-mini and makefile-mini all were first experiments in other *-mini projects but then became clear enough to turn into libraries).

## Compilation

At first I used Eclipse. Later I switched to Makefiles and make and platform specific scripts (.bat for windows and no extension but `#! /bin/sh` at the top for linux) to retrieve the platform specific Makefile from a corresponding branch (using git-archive). I had never written a Makefile before and never used make, this was my first introduction to Makefiles and make.

These first and platform-specific Makefiles I wrote were entirely duplicated. Currently most still are entirely duplicated, as makefile-mini is a W.I.P., but they're no longer platform specific.

## Tests

<div class="row">
  <div class="12u">
    <figure>
      <!-- image-border and no-image-border here as 919px is width of image (i.e. "border-width") -->
      <div id="image-border">
        <img src="/img/personal_project/asterisk_mini/arguments_mini_test.png" id="no-image-border" style="width: 100%;max-width: 919px;">
      </div>
      <figcaption style="text-align: center;">Output of argument-mini-test 0.2.1</figcaption>
    </figure>
  </div>
</div>

The first tests were [tcp-test-scout](https://github.com/Wallby/tcp-mini-test) (which was [renamed to tcp-mini-test](https://github.com/Wallby/tcp-mini-test/commit/385cd226d194f2c9ccc9c123adefab06111565db)) and [tcp-test-match](https://github.com/Wallby/tcp-test-match) for tcp-mini. Each test was in a separate repository.

The discontinuing of tcp-test-match and renaming of tcp-test-scout to tcp-mini-test merged both tests into one (using localhost and the test executable both creating the socket and connecting to it). This also <a title="Select &quot;Load diff&quot; for main.c" href="https://github.com/Wallby/tcp-mini-test/commit/385cd226d194f2c9ccc9c123adefab06111565db#diff-a0cb465674c1b01a07d361f25a0ef2b0214b7dfe9412b7777f89add956da10ecR719-R775">introduced  test macros (see link tooltip)</a> that later became a feature of test-mini.

<div class="row">
  <div class="12u">
    <figure>
      <!-- image-border and no-image-border here as 919px is width of image (i.e. "border-width") -->
      <div id="image-border">
        <img src="/img/personal_project/asterisk_mini/early_test_macro_example.jpg" id="no-image-border" style="width: 100%;max-width: 500px;">
      </div>
      <figcaption style="text-align: center;">An early test macro and it being used</figcaption>
    </figure>
  </div>
</div>

Later [memory leak detection by wrapping malloc and free was added](https://github.com/Wallby/arguments-mini-test/commit/ab9b342f2136e642cd15d168f87bb8b2c7315abf). This feature and the test macros together became the foundation for test-mini.

<div class="row">
  <div class="6u 12u$(small)">
    <figure>
      <!-- image-border and no-image-border here as 919px is width of image (i.e. "border-width") -->
      <div id="image-border">
        <img src="/img/personal_project/asterisk_mini/later_test_macro_example.jpg" id="no-image-border" style="width: 100%;">
      </div>
      <figcaption style="text-align: center;">A later test macro example now using a function for reducing duplicate code</figcaption>
    </figure>
  </div>
  <div class="6u 12u$(small)">
    <figure>
      <!-- image-border and no-image-border here as 919px is width of image (i.e. "border-width") -->
      <div id="image-border">
        <img src="/img/personal_project/asterisk_mini/later_test_function_example.jpg" id="no-image-border" style="width: 100%;">
      </div>
      <figcaption style="text-align: center;">The function called by the macro shown in the previous image</figcaption>
    </figure>
  </div>
</div>

After these two features I switched from Eclipse to make. Using make required switching to a different folder/CLI window to run make there. I added a target `make andrun` to compile and run tests with one command. At first this was fine, but as more projects were started this became confusing. I added a new target `make release` [in arguments-mini](https://github.com/Wallby/arguments-mini/commit/af7e2062d70498b7da2aba933c3511dcbec90a14) which executed a single executable (`test.exe` for windows or `test` for linux). Because of work on other libraries, and tcp-mini being quite usable, [tcp-mini-test](https://github.com/Wallby/tcp-mini-test) hasn't been replaced yet, [arguments-mini-test](https://github.com/Wallby/arguments-mini-test) (which is now archived) has been replaced by a test in arguments-mini.

For lcg-mini I created a different type of test, namely [a command line program](https://github.com/Wallby/lcg) that can generate individual psuedorandom numbers as well as generate .jpg files to see whether any repetition is visible looking at the image.

## Versioning and releasing

[For tcp-mini](https://github.com/Wallby/tcp-mini/releases) and [for arguments-mini](https://github.com/Wallby/arguments-mini/releases) I made several releases. I created [matching releases for arguments-mini-test](https://github.com/Wallby/arguments-mini-test) too when that was still in a separate repository. I also made releases [for tint-mini](https://github.com/Wallby/tint-mini/releases) and for [lcg-mini](https://github.com/Wallby/lcg-mini/releases). Some projects (array-mini, check-mini, clock-mini, sharedlibrary-mini, test-mini and makefile-mini) currently have no releases, which I think is mostly due to the repetition of Makefiles that makefile-mini (which is currently W.I.P.) aims to solve.

All C/C++ \*-mini libraries have a macro variable `#define *_MINI_VERSION` (e.g. for tcp-mini `#define TCP_MINI_VERSION`).

Headerguards use a macro `#define *_MINI_H` named after the file the guard is in (e.g. `#define TCP_MINI_H` for `tcp_mini.h`). Typenames except enum, variablenames and functionnames are prefixed with `*m_` (e.g. `tm_` for tcp-mini). Macros are prefixed with `*M_` (e.g. `CM_` for check-mini). Enums are prefixed with `E*M` (e.g. `ECM` for check-mini).

Though there are \*-mini libraries that have the same function prefix (`am_` for both arguments-mini and array-mini, `tm_` for tcp-mini, tint-mini and test-mini), this is possible as long as each library contains different functions. There is a function `void *m_set_on_print(void(*a)(char*, FILE*));` in several \*-mini libraries, but thusfar this works as there are different types of libraries..
1. libraries intended to be fast thus don't require printing functionality (e.g. array-mini and tint-mini)
2. libaries intended to be reliable thus requiring printing functionality (e.g. arguments-mini and tcp-mini)
3. libraries that contain an entry point and thus can print directly to stdout (e.g. test-mini which contains `__wrap_main` which calls `main`)

All three types of library can be linked together, but there can only be one library of the 2nd type per letter (because of `*m_set_on_print`) and only one library of the 3rd type (as there can only be one entry point). There can be any number of libraries of the 1st type, of which clock-mini and check-mini are an example.