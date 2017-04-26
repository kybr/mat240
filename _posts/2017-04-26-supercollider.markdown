---
layout: post
title:  "SuperCollider"
date:   Wed Apr 26 07:02:56 PDT 2017
categories:
---

## Today...

Download and install [SuperCollider](http://supercollider.github.io).


## Homework 3

> Due Wednesday May 3rd 0600


#### Instructions

*  Complete the homework in SuperCollider
*  Save each problem as a separate SCD files (.scd)
*  Send the SCD files and any other supporting files to karl


### Problem 1 (10%)

Write a patch using a [Pulse](http://doc.sccode.org/Classes/Pulse.html) and control the width with a [Line](http://doc.sccode.org/Classes/Line.html) moving from 0.1 to 0.9 in 20 seconds.


### Problem 2 (15%)

Write a patch using a [SinOsc](http://doc.sccode.org/Classes/SinOsc.html) and [EnvGen](http://doc.sccode.org/Classes/EnvGen.html). Use the envelope generator to control frequency of the SinOsc and trigger it with [Dust](http://doc.sccode.org/Classes/Dust.html).


### Problem 3 (75%)

Create the following [subtractive synthesizer](https://en.wikibooks.org/wiki/Sound_Synthesis_Theory/Subtractive_Synthesis):

<img src="{{ site.url | append:site.baseurl }}/image/synth.png" /> <!-- width="300px"/> -->

This is a model of a classic two-oscilator analogue synth in the style of [Minimoog](https://en.wikipedia.org/wiki/Minimoog) or the [Paia Fatman](http://www.paia.com/fatman.asp). The following is a description of the building blocks shown above.


#### [LFO: Low Frequency Oscillator](https://en.wikipedia.org/wiki/Low-frequency_oscillation)
+ Waveform Types: Sinusoid, Triangle, Saw, Reverse Saw, Square
+ Output: a stream of gain values possibly at the audio rate

This is an oscillator that may be used to drive the controls/parameters of other components of the synth.

(Note: The LFOs in the diagram above may control either or both of the oscillator controls (frequency and gain).)

<img src="{{ site.url | append:site.baseurl }}/image/LFOsection.png" /> <!-- width="300px"/> -->


#### [ADSR EG: Envelope Generator](https://en.wikipedia.org/wiki/Synthesizer#Attack_Decay_Sustain_Release_.28ADSR.29_envelope)
+ Controls: Attack, Decay, Sustain, Release (Note: The values for Attack, Decay, and Release are **durations** (amounts of time in seconds or milliseconds) whereas the Sustain value effects loudness; Sustain is a level, not a duration.)
+ Output: a stream of gain values possibly at the audio rate

This may be used to drive the controls/parameters of other components of the synth.

<img src="{{ site.url | append:site.baseurl }}/image/ADSR_parameter.svg" /> <!-- width="300px"/> -->


#### [OSC: Oscillator](https://en.wikibooks.org/wiki/Sound_Synthesis_Theory/Oscillators_and_Wavetables)
+ Waveform Types: Triangle, Saw, Reverse Saw, Square, Noise (Note: _Sine_ is **not** in this list. That's because the whole point of a subtractive synthesiser is to filter a waveform that is rich in harmonics and sine waves have no harmonics.)
+ Controls: Frequency, Gain either/both of which may be controlled with an LFO or envelope generator.
+ Output: an audio stream


#### [NOISE: Noise Generator](https://www.propellerheads.se/blog/thor-demystified-5-the-noise-oscillator)
+ Types: Pink, White, Brown, Red, Blue, etc. (See [Colors of noise](https://en.wikipedia.org/wiki/Colors_of_noise))

This is really just another form of oscillator.


#### MIX: Mixer
+ Input(s): One or more audio streams (or "channels")
+ Controls: Gain control (per input channel)
+ Output: One audio stream that is a mix of the input streams

(Note: Mixing can be as simple as adding scaled signals together using multiplication (\*) and addition (+).)


#### [VCF: Voltage Controlled Filter](https://en.wikipedia.org/wiki/Voltage-controlled_filter)
+ Input(s): One audio stream
+ Type: [Resonant Low Pass](https://en.wikipedia.org/wiki/Low-pass_filter)
+ Controls: Frequency, Quality (aka resonance), both of which may be controlled by envelope generator or LFO
+ Output: One audio stream (filtered)


#### [VCA: Voltage Controlled Amplifier](https://en.wikipedia.org/wiki/Variable-gain_amplifier)
+ Input(s): One audio stream
+ Controls: Gain which may be controlled by an envelope generator or LFO
+ Output: One audio stream

(Note: Like mixers, VCAs can be as simple as a multiply (\*).)


The synthesizer should be designed as a single SynthDef called "SubSynth." The parameters to "SubSynth" should be an argument. (Alternatively you can use global variables for some or all of the parameters.)

Create at least two instances of “SubSynth” with different parameters and compose a one minute "piece" with these.

Hint: Use Google to search for SuperCollider examples. Explore the built-in SuperCollider documentation system and lookup the docs on each component that you use. Consider implementing a patch from the [Minimoog Patch Book](http://www.synthzone.com/midi/moog/minimoog/MINIMOOG%20PATCH%20BOOK.pdf).

Have Fun!
