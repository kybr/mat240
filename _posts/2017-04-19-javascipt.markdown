---
layout: post
title:  "Javascipt, Browsers, and WebAudio"
date:   Wed Apr 19 09:49:24 PDT 2017
categories:
---

Today we'll discuss several high-level javascript frameworks for digital audio as well as the WebAudio API, the lowest level interface for digital audio in the browser.


### WebAudio
The [WebAudio][] API presents a Graph/Dataflow paradigm whereby the programmer creates audio sources and sinks (called nodes) and connects them together to form an "Audio Graph." The API includes many precompiled, optimized audio generators and effects processors, but also offers a specical kind of node called _[ScriptProcessor][]_ which allows the programmer to write javascipt to produce and process audio. _[ScriptProcessor][]_ is slow and runs in the same thread as the page, but even so, it forms the basis for many browser-based music/sound frameworks. It will soon be replaced by _[AudioWorklet][]_.


### Browser-based Music/Sound frameworks
* [timbre.js][] - functional processing and synthesizing audio in your web apps with modern JavaScript's way like jQuery or node.js
* [tone.js][] - framework for creating interactive music in the browser
* [p5.sound][] - Wrapper for WebAudio for use in the Processing ([p5.js][]) environment
* [Gibber][] - Browser-based live-coding environment
* [genish.js][] - Next level framework inspired by Max's [[gen~][]]; Uses code-generation and single-sample processing


<!--

### Peculiarities of the Browser and Javascipt
* Dynamic memory access/allocation (use single heap)
* Resolving prototype chains (use upvalues)
* Resolving scope (use upvalues)
* Complex branching structures (triggers JIT compiles)

-->

[WebAudio]: https://webaudio.github.io/web-audio-api
[timbre.js]: http://mohayonao.github.io/timbre.js
[tone.js]: https://tonejs.github.io
[p5.sound]: https://p5js.org/reference/#/libraries/p5.sound
[Gibber]: http://gibber.cc
[genish.js]: http://www.charlie-roberts.com/genish
[ScriptProcessor]: https://developer.mozilla.org/en-US/docs/Web/API/AudioContext/createScriptProcessor
[AudioWorklet]: https://github.com/WebAudio/web-audio-api/wiki/AudioWorklet-Examples
[gen~]: https://docs.cycling74.com/max7/maxobject/gen~
[p5.js]: https://p5js.org
