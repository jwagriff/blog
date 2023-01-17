---
title: "How To Fix an Unrecognised Blue Yeti"
description: "Blue Yeti microphones are prone to firmware errors, especially after a lot of use. Learn how to fix an unrecognised Blue Yeti, here."
summary: "Has your Blue Yeti suddenly gone unrecognised in Windows? Fear not. This common problem is easily solved after re-flashing the EEPROM. This guide will help you do just that."
categories: ["Tutorials"]
#showSummary: true
date: 2022-01-12
draft: false
---
The Blue Yeti has undergone a bit of a "glow-up" in recent years. Logitech acquired Blue and all its assets back in 2018, and has since been working to integrate Blue products into its software catalogue. 

For the most part, this transition process has been seamless. Plugging in your Blue Yeti to a system with Logitech Gaming Software installed should have it show up in the program as a tuneable device, with features like Blue Vo!ce.

However, this isn't always the case. If you, like me, bought a Yeti a few years before Logitech acquired Blue, you may have noticed that your microphone will occasionally (or always) show up as a "USB Advanced Audio Device" in Windows sound mixer and device manager. This of course locks you out of any snazzy new features, which can severely impact audio quality. 

Thankfully, not all hope is lost. With some clever driver modifications, you can restore your Yetis functionality to full capacity. Learn how to do it, here.

## Why Does This Happen?

Firstly, you might be wondering what causes this issue in the first place. Unfortunately, the answer isn't very straightforward. A quick Google search shows the problem cropping up all over the internet, with no direct cause referenced by keen-eyed troubleshooters, or Blue/Logitech.

The closest thing I could from Blue themselves was [this tweet](https://twitter.com/nathan_lebeau/status/972939267814187008) where Blue referred to the issue as a "Ghost Microphone". Though, it seems this refers to a hardware fault, which is not the problem at hand.

As a result, we're left only to speculate why this problem occurs. I experienced similar behaviour on a Blue Snowball I had many years ago, and I mostly chocked that up to improper usage through frequent disconnects to my USB ports. The most likely cause is that the chip responsible for holding your Yetis firmware has gradually failed, and needs re-writing. Which is exactly what we're going to do!

## How to Fix Unrecognised Blue Yeti (USB Advanced Audio Device Fix)

Although this issue may sound complex, fixing it couldn't be simpler. All you need is a program called CM64xx from Samson, and a bit of know-how. 

### 1. Finding VID and PID Values

Open Device Manager and navigate to your corrupted Yeti (this should appear as "Microphone (USB Advanced Audio Device)"), right click it, and select "Properties". 

In the window that pops up, select the "Details" tab, and change the dropdown menu underneath "Properties" to "Primary". This should give you a result that looks like this:

    USB\VID_XXXX&PID_XXXX&MI_00\7&2754ceac&0&0000

What we're really interested in here is the four characters next to  `VID_` and `PID_` . Make a note of these for the next step. 

### 2. Connecting to the Yeti

[Download CM64xx](https://samsontech.zendesk.com/hc/en-us/article_attachments/210570827/Meteor_Mic_firmware_repair.zip), and open it up to the "USB Config" tab on top. 

*Mirror Link Coming Soon*

Back in CM64xx, cast your eyes to the bottom of the USB Config screen, specifically the  `VID` and `PID` section. In here, punch in the values you gathered from step 1 and click "Connect". 

After this, you may see a dialogue box pop up containing the error "EEPROM Empty". Feel free to ignore this and just click Accept. 

### 3. Backup the Broken Firmware

Now that we're connected to the Yeti, the first thing we'll do is back up the existing EEPROM (even if it is reportedly empty) just in case anything goes wrong. 

To do this, click the "EEPROM > File" button at the bottom of CM64xx. Be sure to choose a memorable name for this, such as "backup.bin". 

### 4. Flash the fixed Firmware

With your firmware backed up, we can now start the flashing process. Different model microphones have different values required for here, so I'll drop a table with these at the bottom of this section.

At the top of CM64xx, you'll see sections labelled "ID" and "String". In the ID section, fill in the corresponding `VID` and `PID` values for your microphone. The same goes for the Manufacturer String and Product String. 

To find your devices Serial String, open up the EEPROM backup you made in step 3 in a hex editor of your choice.

Somewhere around lines 60 - 80, you'll see a 20 character list of numbers separated by underscores and forward slashes. Copy this and enter it into the Serial String section of CM64xx.

Next, navigate to the Volume, EQ and Misc. Config tabs and ensure all your values line up with those listed for your microphone. I've uploaded screenshots for the standard Yeti to this folder on my Google Drive (Link coming soon!).

One finished, click "SAVE EEPROM" at the bottom of CM64, and the program will flash your new firmware.

#### Blue Yeti USB Configurations

| Model              | VID | PID | Manufacturer String | Product String |
|--------------------|-----|-----|---------------------|----------------|
|Blue Yeti (Standard)|B58E |9E84 |Blue Microphones     |Yeti Stereo Microphone |

More models coming soon.

### 5. Sanity Checks

Once you've flashed the EEPROM, a dialogue box will pop up telling you to disconnect and reconnect your device. Close the dialogue box and do as it says.

When your Yeti reconnects, it should be fixed! One way to fully ensure this is to open Logitech Gaming Software and see if your device comes up.

## Looking for More Tech Tutorials? 

There you have it! You can now get back to using your Yeti like before, and perhaps even start to enjoy the previously untapped potential of Blue Vo!ce. 

If you're looking for more tutorials, be sure to check out some of my [other posts](https://jwagriff.work/posts/). Need something specific covered? Reach out to me on Twitter and I'll see what I can do. 

Image Credit: zXenial / Pixabay