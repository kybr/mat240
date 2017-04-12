---
layout: page
title: Syllabus
permalink: /syllabus/
---

	MAT 240A Spring 2017
	When: W F noon-2pm
	Where: Elings 2809
	Instructor: Karl Yerkes Ph.D. 
	TA: Qiu Weihao
	http://mat.ucsb.edu/240/A
	http://lists.create.ucsb.edu/mailman/listinfo/240
	

This course is an introduction to the many facets of audio programming. Audio programming can take many shapes, and requires different tools and practices for artistic projects, scientific research or industrial applications. This course will present an overview of these different aspects of audio programming while introducing and exploring key concepts that permeate most audio programming projects.

We explore a diverse palette of tools, covering the most common applications and challenges in audio programming. Our tools include high level and domain-specific languages useful for prototyping multimedia works (e.g., Pd, Max, SuperCollider, and ChucK), data science and engineering environments used in acoustics, psychoacoustics and DSP research (e.g., IPython Notebook, FAUST, MATLAB), and low level languages and libraries necessary for performant, portable, and maintainable applications (e.g., C/C++, RtAudio, Gamma).

Although the course cannot hope to explore the presented languages and topics in all their detail and complexity, its aim is to give the student the ability to make decisions about the environment and tools for their particular projects and target platforms, having a clear understanding of the challenges and constraints present when working with audio. It should also provide a starting platform for further exploration and learning into particular tools and techniques.


## Topics
- Digital Audio, sampling and representation.
- Events and asynchronous data in audio contexts.
- File and Realtime I/O concepts and APIs.
- Concurrency (or lack thereof) in audio


## Computing contexts
- Single powerful computer (e.g., your laptop)
- Mobile, less-powerful computer (e.g., your phone)
- Embedded system (e.g., Raspberry Pi or Teensy)
- Several Distributed/Networked computers (e.g., CREATE ensemble, NETFLIX)
- Virtual machine / Browser environment (e.g., Gibber, WebAudio)
- Offline (as opposed to Real-time)

We explore what characteristics each of these contexts share and how they differ.


## _Not_ Topics
- Spectral tranformations
- Music Information Retrieval 
- Audio Synthesis Techniques
- Sonification
- Audio Effects
- Spatial Audio

As these topics are covered in later courses (namely 240 B-F), we will not cover them in this course. That said, we may incidentally touch on some of these in the course of our work.


## Software

We will use many tools in this course. Look to the [Install]({{ site.url | append:site.baseurl }}/install) page for help with software installations.

- Python
- Csound
- Javascript (WebAudio and Gibber)
- Pd
- Max/MSP
- Jack/JackTrip
- C/C++


## Schedule

<style>
table { border-collapse: collapse; }
table, th, td { border: 1px solid black; }
th, td { padding: 15px; text-align: left; }
</style>

|Week |Topics|
|-----|:-----|
|  1  | - Defining the scope of Digital Audio Programming and of this course <br/> - Introduction to audio programming using data science and engineering tools <br/> - Audio as a list of samples that can be handled as vectors, and mathematical operations on audio vectors|
|  2  | - Using a domain specific language for music: Csound <br/> - Musical theory, concepts and ideas in code <br/> - History of Computer Music Languages|
|  3  | - Introduction to Javascript and the WebAudio API |
|  4  | - Interactive music systems <br/> - Live coding and interactive prototyping in Gibber and ChucK <br/> Understanding and working with a dynamic audio chain |
|  5  | - Dataflow languages: Pd and Max/MSP <br/> - Working with event based programming |
|  6  | - Programming in C<br/> - Using build systems and Makefiles for audio projects<br/> - Overview of File I/O APIs |
|  7  | - Real-time I/O and I/O APIs <br/> - Callback versus blocking interfaces <br/> - Considerations for real-time audio programming |
|  8  | - Asynchronous events and callbacks versus event polling |
|  9  | - C++ and Object oriented programming in relation to audio <br/> - Using source control for version tracking and collaboration <br/> - Introduction to Gamma and AlloSystem |
| 10  | - Plugin APIs overview <br/> - Pd/Max "externals" |

<br/>

# Final project

The final project should implement some original idea by the student using any of the systems reviewed (or another similar system). The project should concern some topic of interest to the student and should tackle some difficult idea or project.


## Grading

- 40% Homework
- 40% Final project
- 10% Theory assignment
- 10% Class participation


## References and Resources

There is no single textbook for this course, however the following resources may be useful at different stages:

- [The SuperCollider Book](http://supercolliderbook.net) Wilson, Cottle and Collins 2011
- [bang Pure Data](http://pd-graz.mur.at/label/book/bangbook.pdf) 2006
- _The Audio Programming Book_ Boulanger and Lazzarini 2010
- Smith 1999: _The Scientist and Engineer's Guide to Digital Signal Processing_ [www.dspguide.com](http://www.dspguide.com)
- Julius O. Smith III: [_Introduction to Digital Filters_](https://ccrma.stanford.edu/~jos/filters)
- [_Software Carpentry_](http://www.software-carpentry.org)
- _The Computer Music Tutorial_ Roads
- [The Theory and Technique of Electronic Music](http://msp.ucsd.edu/techniques/latest/book.pdf)

