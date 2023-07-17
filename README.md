# Introduction
BumWings is an ergonomic keyboard design that has two variants:  one that uses the Waveshare RP2040-zero board which features a Raspberry Pi RP2040 MCU, and another that uses the Xiao Seeed family of controllers.   This design is my first attempt at an all-new keyboard PCB design, but obviously it has been influenced by many other keyboard designs (both open-source, closed-source and commercial).

## Design and Implementation

BumWings uses an "un-split" angled ergonomic matrix that has columnar stagger with moderate pinky splay, and features dual inverted T-clusters and modest thumb key clusters.  It is a fairly large board that also gives space for the hands to stay apart and rest at an angle, which works well for me.

The controller board can either be soldered directly to the PCB, or socketed pin headers can alternately be used.

Credit is given to Pete Johanson for the Xiao footprint, circuit design and other aspects from his [revxlp keyboard design](https://gitlab.com/lpgalaxy/revxlp).

This design uses Kailh "Choc" PG1350 key switches.  The board can either be used bare (not recommended) or installed in a case.  I have uploaded a set of PCB case files for a Corne-style board arrangement (with both top plate and bottom plate).  Other case options are still a work in progress.

## Revisions

The original designs (labeled as "v001", committed in December 2022 and January 2023) represent my first attmept to create a keyboard PCB design.  I learned several things, including the undeniable fact that relatively large PCBs are somewhat more expensive. 

I also learned that my hand-soldering skills were **not** that great.  

These learnings were applied to the "revised" or "remixed" designs (labeled as "v001R", committed in July 2023) which improve on the original "v001" design.  These are in the "v001R" subdirectory.

## Pictures - Work in Progress

Here is a picture of my first prototype build of the initial "v001" RP2040 variant with 54 keys.  It has Kailh Choc Robin switches (mostly).

![](doc/bumwings_v001_prototype_first_build.jpg)

Here is a picture of the new "v001R" RP2040 variant with 64 keys.  This is now my "daily driver" keyboard.  It has Kailh Choc Brown switches (mostly).

![](doc/bumwings_v001R64_rp2040zero_build_daily.jpg)

Here are two pictures of the new "v001R" Xiao variant with 64 keys.  This keyboard will be a gift for a friend.  It has Kailh Choc Jade switches (mostly).

![](doc/bumwings_v001R64_xiao_sd_build_wip.jpg)
![](doc/bumwings_v001R64_xiao_sd_build_keycaps.jpg)




(more pictures coming soon)

