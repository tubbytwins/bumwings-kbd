# V001R

I used JLCPCB to build the prototype PCBs for this version.  These work nicely, perhaps even better than the original "v001" designs.


## List of Variants

*   "pcb_R55_rp2040zero_sd" - simplified, remixed, 55-key direct-soldered PCB based on the Waveshare RP2040 "zero" controller
*   "pcb_R55_xiao_sd" - simplified, remixed, 55-key direct-soldered PCB based on the Seeed Xiao controller
*   "pcb_R64_rp2040zero_sd" - simplified, remixed, 64-key direct-soldered PCB based on the Waveshare RP2040 "zero" controller
*   "pcb_R64_xiao_sd" - simplified, remixed, 64-key direct-soldered PCB based on the Seeed Xiao controller



## Explanation

These variants are different from the "v001" designs in several ways:

*   The overall length of the board was reduced, by about 1 inch.  This brings the hands closer together, but it's still a comfortable arrangement (at least for me).
*   The two hands were rotated "outwards" (i.e., left hand counter-clockwise, right hand clockwise) by a few degrees.  It's a subtle change that helps to reduce the overall width of the board.
*   The shift registers from "v001" (which are 74HC595PW components, in TSSOP-16 size) are now 74HC595D components (in SOIC-16 size) as the former were quite difficult to hand-solder (at least for me).  I messed up at least one prototype board with the TSSOP-16 components, then I learned that the SOIC-16 components were significantly less prone to soldering mishaps.
*   All components are now attached to the top side of the PCB (instead of the bottom side).
*   The case plates were removed, and the new designs are single-PCB caseless builds.  However, you are free to build a case around these if needed.
*   I switched away from the Kailh Choc hot-swap sockets, and went for direct-soldered switches instead.  I have nothing against the hot-swap sockets, but wanted the board design and construction to be simpler for these variants.

I also took the liberty of experimenting with the layout and the number of keys, as follows:

*   The "R55" variants add an extra 1.5U key in the center (between the thumb modifier keys).  You can use this as a space bar, a dedicated enter (carriage return), a layer key or any modifier.
*   The "R64" boards add 10 keys along a new top row, above the alpha keys (for all fingers except the pinky).  You can use these for other commonly accessed symbols, macros, or even delete/tab keys as desired.  The thumb spacebars are also now 1.5U keys instead of 2U keys, and the thumb cluster has been moved upward slightly, in order to reduce the overall width of the board.  In practice, a 1.5U spacebars are quite usable, and you could probably use a 1.75U spacebar (if the key caps were available).




## Pictures

The board renders for the 55-key and 64-key Waveshare RP2040-zero variants are shown below:

![](doc/bumwings_v001R55_rp2040zero_board_render.jpg)

![](doc/bumwings_v001R64_rp2040zero_board_render.jpg)


The board renders for the 55-key and 64-key Xiao Seeed variants are shown below:

![](doc/bumwings_v001R55_xiao_sd_board_render.jpg)

![](doc/bumwings_v001R64_xiao_sd_board_render.jpg)




## Bill of Materials

## All variants

Diodes:  D_SOD-123 (either 55x or 64x)

Sockets:  none (since key switches are direct-soldered)

Key caps:  MBK (either plain, or with legends, at your discretion)

Other resistors/etc:  none



### Waveshare RP2040 variant

MCU:     Waveshare RP2040 "zero" (23-pin module with USB-C port) - you can find these on Amazon for a higher price, or on Aliexpress or eBay for a lower price.  They can either be plain, or with pre-soldered pin headers.

### Xiao Seeed variant

MCU:     Xiao Seeed controller of your choice - you can find these from many suppliers.

Shift Register:  74HC595D (in SOIC-16 format) - you can find these from many suppliers.  The 55-key variants use 1 of these, and the 64-key variants use 2 of these in a chained configuration.


## Future Plans and Possibilities

*   A wireless nRF52840 variant, perhaps based on the Waveshare Core52840 module or the HolyIOT 18010 module.
*   A wired ESP32 variant, based on a nice compact ESP32-C3 controller board that I found on AliExpress.  It's slightly smaller than the Waveshare RP2040 "zero" controller and slightly larger than the Xiao Seeed controller.
*   A simple PCB plate (top only) to help stabilize the key switches and make swapping key-caps more robust.




