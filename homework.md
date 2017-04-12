---
layout: page
title: Homework
permalink: /homework/
---

<style>
table { border-collapse: collapse; }
table, th, td { border: 1px solid black; }
th, td { padding: 15px; text-align: left; }
</style>

Unless we say otherwise, **all assignments are due by 0600** (6AM) of the posted due date. If I ask you to email me your homework submission, the email subject line must contain the following text `MAT 240A HW x FirstName LastName`.
- - - - -

## Homework 2

	Homework 2: Csound
	Due: 2017-04-19 0600
	

### Instructions
- Complete the homework in CsoundQt
- Save each problem as a separate .csd files
- Create a folder with all the .csd files
- Zip the folder and email it to me


### Problem 1 (40%)

#### Create the following two instruments
1. Sine with amplitude modulation
2. Sine with frequency modulation

Use sinusoids for all signals. Modulate at the audio rate, not the control rate. Make sure you are not using a control (k) rate oscillator to modulate. Each instrument should be controlled by an ADSR envelope with parameters of your choosing.

##### Each instrument should take these parameters:
- p2: Time (the note should start)
- p3: Duration (of the note)
- p4: Amplitude
- p5: Frequency
- p6: Modulation Amplitude
- p7: Modulation Frequency


#### Create a score for the two instruments

You may write a score manually, by typing each line, or you may use a spreadsheet to generate a score. Since a score is just a list of text lines containing instrument parameters, you may use any programming lanuage to generate a score. For example, here's a simple score generator in python:

```python
%pylab inline
time = arange(10)
duration = ones_like(time)
amplitude = ones_like(time) * 0.5
frequency = linspace(220, 880, 10)
for t, d, a, f in zip(time, duration, amplitude, frequency):
    print("i 1 %f %f %f %f" % (t, d, a, f))
```

<pre>
i 1 0.000000 1.000000 0.500000 220.000000
i 1 1.000000 1.000000 0.500000 293.333333
i 1 2.000000 1.000000 0.500000 366.666667
i 1 3.000000 1.000000 0.500000 440.000000
i 1 4.000000 1.000000 0.500000 513.333333
i 1 5.000000 1.000000 0.500000 586.666667
i 1 6.000000 1.000000 0.500000 660.000000
i 1 7.000000 1.000000 0.500000 733.333333
i 1 8.000000 1.000000 0.500000 806.666667
i 1 9.000000 1.000000 0.500000 880.000000
</pre>


### Problem 2 (60%) 

Create an instrument which produces bell-like sounds by using [additive synthesis](https://en.wikipedia.org/wiki/Additive_synthesis) (i.e., using many sine wave oscillators together to create the timbre).

Use an exponentially decaying envelope to decide the amplitude of each oscillator. We do this by feeding the output of the exponentially decaying envelope into the amplitude of the sine wave oscillator as shown in this graphic:

<img src="{{ site.url | append:site.baseurl }}/image/SineWithExpEnvelope.png" width="100px"/>

Create the instrument using 11 oscilators and 11 envelopes with parameters like these:

| Partial | Frequency        | Amplitude | Duration |
|---------|------------------|-----------|----------|
|    1    | F * 0.56         |    1.00   |   1.000  |
|    2    | (F * 0.56) + 1   |    0.67   |   0.900  |
|    3    | F * 0.92         |    1.35   |   0.650  |
|    4    | (F * 0.92) + 1.7 |    1.80   |   0.550  |
|    5    | F * 1.19         |    2.67   |   0.325  |
|    6    | F * 1.70         |    1.67   |   0.350  |
|    7    | F * 2.00         |    1.46   |   0.250  |
|    8    | F * 2.74         |    1.33   |   0.200  |
|    9    | F * 3.00         |    1.33   |   0.150  |
|   10    | F * 3.75         |    0.75   |   0.100  |
|   11    | F * 4.07         |    1.33   |   0.075  |

<br/>

Experiment with different frequencies and durations by creating a score. Now, create a new instrument (with number 2) by starting with the bell but changing the partial relationships and envelopes (i.e., mess with the values in the table).

<br/>
<br/>

- - - - - - - -

<br/>
<br/>

## Readings 1: ADC and DAC

Read the [syllabus]({{ site.url | append:site.baseurl}}/syllabus).

Read [Chapter 3](http://www.dspguide.com/CH3.PDF) of [_The Scientist and Engineer's Guide to Digital Signal Processing_](http://www.dspguide.com/pdfbook.htm) by Steven W. Smith, Ph.D.



## Homework 1: Audio in python

### Instructions

1. Complete the homework using IPython/Jupyter Notebook.
2. Add section titles and comments in your notebook as you work.
3. Save your work as an IPython Notebook File (.ipynb).
4. Make sure your notebook executes *all* cells without errors.
5. Compress your notebook and file using zip or gzip.
6. Use dropbox or some similar service to email me _a link to_ the compressed notebook.


### Problem 1 (25%)

Write a python script to generate a 5 second audio file of a dual tone alarm sound. The tones should be at 600 Hz and 800 Hz. They alternate every 500 ms.

Use two sinusoidal oscillators to generate the tones and a square oscillator to alternate between them. "Taper" the square oscillator for smoother transitions.

The output file should be mono sampled at 22.5 KHz.


### Problem 2 (35%)

Write a python script to generate an audio file comprised of all the tones available in DTMF (dual-tone multi-frequency) signaling starting with a dial tone. After a 300 ms dial tone, the tones should be 200 ms long followed by a 50 ms silence. The dial tone is a 350 Hz and 440 Hz signal at equal amplitude. For the signaling tones, refer to the table below. Create this sequence: [dialTone, 1, 2, 3, A, 4, 5, 6, B, 7, 8, 9, C, \*, 0, #, D].

| Hz  | 1209| 1336| 1477| 1633|
|-----|-----|-----|-----|-----|
| 697 |  1  |  2  |  3  |  A  |
| 770 |  4  |  5  |  6  |  B  |
| 852 |  7  |  8  |  9  |  C  |
| 941 |  *  |  0  |  #  |  D  |

Table: DTMF keypad character

The output file should be stereo sampled at 22.5 KHz.

Generate a spectrogram of the signal and save it as a jpeg file.


### Problem 3 (40%)

Write a function in python that accepts a string of DTMF keypad characters, parses it, and generates the corresponding DTMF Tones (200 ms) and stores them in an audio file.

Expand functionality by adding a silence character (50 ms). Introduce frequency offset characters and use them to shift the frequencies up or down by a constant offset.

Compose a "piece" using the function.
