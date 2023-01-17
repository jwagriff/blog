---
title: "Polybar Build Guide"
description: "It's hard to find good quality, original Guitar Hero controllers these days. Why not build your own? Find out how to build a Guitar Hero controller, here. "
summary: "This article provides a step-by-step guide on how to assemble the Polybar, a 3D printed Guitar Hero controller. It covers everything from preparing the printed parts to wiring and flashing firmware."
categories: ["Tutorials"]
#showSummary: true
date: 2022-01-29
draft: true
---
It's no secret that buying Guitar Hero controllers has gotten very expensive lately. While you may be able to get lucky at thrift stores, there's no guarantees out there for quality. Let's not forget, five-fretted Guitar Hero controllers were first made all the way back in 2006; so it's no surprise that a lot of them have seen better days.

Fast forward to 2023 and there's some glimmers of hope. The Clone Hero community has banded together to create all sorts of modifications like mechanical frets, 3D printable, drop-in replacement parts, and even full guitar bodies. 

My friends and I have recently been jamming out on Clone Hero in the evenings, and as we bashed away at our now almost 16 year old guitars, we got to thinking: are there any good quality, fully 3D printed guitars out there? 

After hours of scouring Thingiverse, one of which stood out to us the most. Introducing: the Polybar, courtesy of [roadsidebomb.](https://github.com/roadsidebomb/)

In this article, I will be providing a guide on how I personally built my own Polybar. Many of the steps have already been discussed in other guides, such as those that explain how to retrofit an Arduino into an official controller, but the Polybar is a little different due to it being entirely 3D printed.

This guide includes the instructions I followed on preparing the printed parts, as well as wiring and configuring the electronics. Let's begin! 

## Pre-requisites

Before proceeding, you'll need the following:

 - 3D printer and filament
 - 7x full-size, mechanical keyboard switches (5 linear, 2 clicky)
 - 2 M5 20mm bolts
 - 1x M5 35mm bolt
 - 3 M5 x 10 x 7mm threaded inserts
 - 3x 6x6x4.5mm microswitches
 - 1x Arduino compatible joystick board
 - Colour-coded strands of AWG 30-32 wire
 - 1x Adruino Pro Micro (or clone)
 - 1x USB-C cable
 - Soldering iron
 - Hot glue
 - Sandpaper or filing tool
 - Pliers
 - Super glue
 - [Ardwiino Guitar Configuration Tool](https://sanjay900.github.io/guitar-configurator/) by Sanjay
 - [The latest project files](https://github.com/roadsidebomb/Polybar-Minibar-3D-Print-Files) (credits to roadsidebomb on Github) **OR** These modified files if you're following the way I built mine.
 - Heatgun (Optional)
 - Solder flux (Optional)

## Print Settings

![3D printed Polybar](./images/3d%20printed%20parts.jpg)

First we must discuss the printing process. Once downloading the files from roadsidebomb's Github, simply open them in your preferred slicing program (I'm using Prusaslicer). 

Parts can be printed in two batches: In one batch you'll have the internal boards used to hold switches in place, as well as any button heads; in the second, you'll have the body of the Polybar itself. The body can be printed either with or without an extension that sits between the strumbar and the frets to give it a more traditional controller length.

The only settings worth noting are as follows: 

    Infill: 20%
    Infill type: Gyroid
    etc
	
## Test Fitting

Before we assemble anything, it's important to test fit the parts to ensure everything plays together nicely. It's likely you'll need to make some minor adjustments to the guitar before starting the main portion of the build. Nothing too extreme, we just want to remove as much support material as possible on the internal boards, dovetail connectors, and well, anything else.

After removing any supporting material, one area we'll want to focus on is the dovetail connectors for each part of the Polybar body. These need to be sanded to the point where the inside feels smooth to the touch. Failure to do this will result in gradual bends later down the line.

![Smooth internal dovetail joints](./images/sanded-dovetail-connectors.jpg)

One you're satisfied that everything is smooth, the test fit can begin!

**Note:** The Polybar comes with an optional extension to give a slightly longer neck. I decided to use this, and glued the whole top section together at the dovetail joints to make disassembly much simpler. This is optional, but just thought you should know!

### Strum Case Assembly

Before assembling the strum case, take the two internal strum bar boards and place a blue switch in either one. On top of the switch, you'll need the rectangular shaped switch cap to be placed like so:

![Strum bar switches](./images/strum-bar-images.jpg)

On the bottom half of the strum case and insert the internal boards. The joystick board goes at the bottom, the two blue switch holders go in the middle, and the two microswitch holders go at the top. There are notches along the small railings on the inside of the case to help you place things in the right location, so I tend to slide these along until I get a good fit.

![Bottom strum case assembly](./images/bottom-strum-case-assembly.jpg)

Now we move to the top section of the strum box. We first want to get the actual strum bar itself installed. To do this, lay the strum bar itself inside and then take the two plungers and insert them through the raised sections located either side of the strum bar. Flip the piece around and move the strum bar from up to down and ensure everything operates smoothly. If it does, flip the board around once more and place the plunger covers over the top of the raised sections. These will prevent the plungers from accidentally falling out. 

![Strum bar assembly](./images/strum-bar-assembly.jpg)

Another thing to do would be to check that the buttons fit into their respective slots. The top two buttons are the same size, and the bottom button is slightly smaller. We won't be able to check the joystick head fit just yet, but you can always lay it on top to see if it covers the hole. Be sure to remove these after you've verified that everything fits.

![Checking strum case buttons](./images/checking-strum-case-buttons.jpg)

### Fret Button Assembly

To test the fret button assembly, we first want to place the linear switches into the 5 slots on the internal board. 

**Note:** The switches should be placed in the board with the smooth side facing downward. 

![Bare fret switches](./images/bare-fret-switches.jpg)

Simply press each switch into place until you hear a click. After that, insert the switch caps into each switch

![Switch caps](./images/switch-caps.jpg)

We can now slide the fret board into the bottom half of the neck shell. Similarly to the strum case buttons, there are notches to help you find the right location.

Once this is in place, take the fret buttons and place them on top of each switch cap. Line them up so that they're all straight to make the next step a bit easier.

![Fret buttons](./images/fret-buttons.jpg)

The fret buttons have a tear drop cut out on the bottom to make removing them a bit easier, but the orientation that you install them in doesn't really matter (These buttons require some sanding, so I tend to orient them so that the sanded side is facing away from me when holding the guitar).

![Fret button teardrops](./images/fret-button-teardrops.jpg)

### Closing the Polybar

Looking at the top side of the strum bar, the bottom has a triangle that is designed to be inserted into the bottom casing at an angle. 

![Angled top case assembly](./images/angled-top-case-assembly.jpg)

To fit both sides of the polybar together, simply lay the top of the shell into the bottom at an angle. You'll see that the trianglular piece above slots into a cut out on the bottom shell. Once these are lined up, lower the top portion downward until both pieces clamp together. You may need to wiggle the pieces around a bit to get everything sliding down correctly, but take your time; it'll fit!

![Lowering the top part down](./images/lowering-the-top-part.jpg)

**Note:** If you too glued the top part together, try moving from the bottom of the shell upward, clicking each part together as you go. This should avoid excess strain on the joints. 

If everything fits; congratulations! Now on to the shell.

### Shell Assembly

Shell assembly will vary depending on which guitar shape you choose, but the process is relatively uniform.

Each shell comes in two parts; one top, one bottom. The top section can (and probably should) be glued together to ensure a nice even fit.

If your Polybar is assembled, you first need to take the top case off and remove the two neck pieces. This leaves you with just the strum case. The strum case slides into the shell at an angle, and can sometimes feel a bit uncomfortable. Be persistent, and don't be afraid to bend the plastic pieces slightly.

If the fit is too tight, feel free to file away some of the plastic in the lower portion. I do recommend doing this, especially if you'll be swapping frames out quite often. 

**Note:** In the pre-requisites, I have listed alternative downloads for the Xplorer shell that my friend modified. This allows the Polybar and the frame to be secured via one M5 35mm bolt. This makes disassembly much quicker.