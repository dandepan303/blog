---
title: Hardmodding My Switch
description: Hopefully I don't turn it into a paperweight
slug: hardmodding-my-switch
date: 2024-09-13 08:34:23+0000
image: cover.jpg
categories:
    - Hardware
tags:
    - Nintendo Switch
weight: 1       # You can add weight to some posts to override the default sorting (date descending)
---

> ## QUICK WARNING
>
> This is not a comprehensive guide. Just a blog post about how I did it myself. If you want to "mod/hack" your switch, I recommend following thourough guides on [switch.hacks.guide](https://switch.hacks.guide) and following the dissassembly guides on [ifixit](https://www.ifixit.com/Teardown/Nintendo+Switch+Teardown/78263?srsltid=AfmBOopafqIlha4w_7wViLBNHRTsR9xevz8mXbvGGDWJCnt6BXANPRET). As always, you, and only you, are responsible for what happens to your console.

## Background

I’ve had my Nintendo switch sitting around and collecting dust for a while now. My interest was piqued when I learned about the combination of [box64](https://github.com/ptitSeb/box64) and [wine64](https://winehq.org), two programs that emulate x86 architectures and windows applications efficiently. I was even more excited when I learned about the [switchroot](https://switchroot.org/) project, a project that allows people to run Ubuntu 24.04, Fedora 39, and Android 14 on the switch natively!

## How powerful is the Switch?

After doing a bit of research, the switch runs on the Nvidia Tegra X1, an 8-year-old veteran ARM processor that still packs a bit of a punch!

Infographics non overclocked

Normally, the Switch’s cpu is underclocked and undervolted to a meager 1 ghz (for thermals and battery life). On the other hand, the X1 is rated to go as fast as 2 ghz, and with the correct overclocking, we can achieve 2.3 ghz on the cpu, something on the gpu, and something on the ram. This is more on par with the Snapdragon something, very impressive for a processor of this age.

Infographic oc

## How can I jailbreak my switch?

The main factor in the method of jailbreaking your switch depends on your model. There are 2 main “models” for the original switch Erista 2017 - early 2018 models (also referred to as unpatched or V1) and Mariko (patched, V2). You can find out which one you have at —- and putting in your serial number.

For Erista consoles, there is a bug that exists, allowing you to short 2 pins on the right JoyCon rail to bypass BOOT0 and inject a payload for your switch to boot instead of HorizonOS (normal switch OS). This can be achieved by soldering a joy-con, or using a paperclip or rcm jig.

For Mariko (V2) consoles, they are only able to be jailbroken by using a modchip, which requires soldering 4 tiny contacts to 2 capacitors on the cpu to “voltage glitch” the cpu into booting payload.bin on the microsd card instead of BOOT0. The modchip works by infiltrating the communication between the main board and the sysnand. This is an extremely condensed explanation, and if you want to a full one, you can visit this website.

For Nintendo switch oled models, you also need a modchip, but the process is much more lengthy and requires a microscope.
I, personally own a Switch V2, so I will go down the modchip route.

## 6-year-old flux and 215C Sticks

> Photo by [Pawel Czerwinski](https://unsplash.com/@pawel_czerwinski) on [Unsplash](https://unsplash.com/)
