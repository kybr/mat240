---
layout: post
title:  "Csound, Music DSLs, and some history (continued)"
date:   Fri Apr 14 11:30:14 PDT 2017
categories:
---

## History

Barry Vercoe <https://www.youtube.com/watch?v=OrC8DSOsv-Q>

Roads, Mathews, and Chowning <https://www.youtube.com/watch?v=Hloic1oBfug>

## Csound

Csound reads and compiles Csound (.csd) files, and produces audio output. Command line flags (options/settings) change the bahaviour of the Csound compiler.

Csound may be embedded into other programs that are written in other languages (i.e., C++, Java, Python, Lua). This is a nice feature to have in a Music DSL. 

### Rates

In Csound, audio processing is _executed_ sample by sample, but _controlled_ in blocks of samples. We may think of these as rates: the audio rate and the control rate. Commonly, the audio rate (or audio playback sample rate) is 44100 Hz and the control rate (or block rate) is some power of two division of the audio rate (e.g., 128, 256, 512).

Csound also has two other rates (or we can think of them that way), the _i_ rate is...

### Orchestra

The orcestra section defines settings for audio rendering such as the sample rate, control rate (block size), number of channels, and maximum amplitude. Moreover, it defines the instruments, a group of connected of opcodes that together process input parameters to output sequences of numbers representing audio samples.

- Variables start with these letters:
  + a -> audio rate
  + k -> control rate
  + i -> initialization rate
  + S -> string
  + f -> "spectral" (frequency domain) signal
  + g -> global (default is scoped to intrument)

### Score

A score is primarily a list of events, one per line, each with at least three parameters: instrument number (p1), start time (p2), and duration (p3). Paramters p4, p5, etc. are optional and their meanings are defined by the instrument.

Csounds concept of music/sound is a series of events triggering sound producers.

