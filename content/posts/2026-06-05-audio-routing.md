---
date: '2025-06-05T17:29:59-04:00'
draft: False
title: 'My current e-piano audio setup 🎹'
slug: "keyboard-audio"
author: John Craven
categories: 
- music
tags:
- music production
---

## A little background

I bought a digital piano (Roland FP-30x) last year after wanting to get back into paino for a long time. I played a bit of piano when I was young and then played guitar on and off for a few years. I'm still playing at a beginner level but getting back into playing as a hobby has been fun. Most of the time I'm playing with sheet music or video lessons (I've been having a good time with [Pianote](https://www.pianote.com/)), but also wanted to dig into some more music production and playing with synths / VSTs.

Getting the audio routing setup right took me a bit of time and playing around with settings, so I thought it might be fun to share. I wanted to get a few things out of this...

1) Playing the piano just by itself should work without any hassle
2) I should be able to monitor the piano and listen to videos through the same headset/speakers
3) I should be able to set up virtual instrument plugins for DAWs on my computer, play them with the keyboard, and monitor everything through the same headset/speakers

## The setup

None of this was ultimately too complicated but there were a few tricks to get it working just right. Here's a basic diagram of the physical setup below.

```goat
    +- bluetooth ----- ipad  
    |                 
  piano ----- usb -- computer  
    |
    +---+---- onboard speakers
        +---- headset
        +---- amp --- standalone speakers
```

The piano sits at 90° to my desk, so it was easy enough to run a long USB cable directly into the back of my computer and leave it there. I think it may be more common for people to set this up with a laptop but I like having a permanent setup with my desktop computer.

OK, so with this setup a few things work out of the box...

* The headset and speaker connections are easy enough. In practice I'm usually using a headset since I'm currently in an apartment, but the onboard speakers are also pretty good.
* Bluetooth connection on the FP-30x has 2 modes - audio or MIDI. I'm almost always connecting with audio to listen to videos or a backing track. Adjusting the volume on the ipad lets me adjust the relative levels to the piano and the piano volume effectively becomes the master
* Using the piano as a midi controller also works pretty well out of the box, you may need to fiddle a bit with low latency audio drivers.
* To use the same headset for a DAW or virtual instrument then I just set the audio out channel to the FP30x from the USB connection, thankfully it lets you do both MIDI in and audio out through the same connection... not sure if that is standard?

But this left a few issues to troubleshoot

* When using the piano as a midi controller you also get the default piano sound doubled on top of it
  * I missed this setting in the manual but one of the function keys on the FP30-X is built for this. They call it "local control" but a simple hotkey will disable the onboard sound when playing with a virtual instrument
* ipad is a little small for sheet music
  * I went luddite mode on this one and bought a printer 😅. For loose sheet music I'm a bit messy right now but I'll get a system going for that when I need it. I caught a [tip from youtube](https://www.youtube.com/watch?v=OYuda9tPBR4&t=343s) to take some tape and bind loose sheet music like little books which helps keep pieces together. Playing smaller chunks on the iPad is still nice but I like the option to fall back to paper.
* The default metronome volume is pretty loud on the FP30x
  * Again, there was a trick for this in the manual. Hotkey function on C5 lets you lower the metronome volume. I haven't figured out how to make this persist after turning off the piano though

Overall, the setup is working well right now. I play a lot of early mornings or evenings so the headset is nice. Having the setup be fairly permanent also makes it a lot easier to jump in and play a little bit when I find time outside of practice sessions.
