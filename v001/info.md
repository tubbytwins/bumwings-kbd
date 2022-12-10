# More Information about BumWings

## History and Design Goals

I've been using TypeMatrix keyboards (both EZR-2020 original and EZR-2030) for nearly 2 decades.  In 2004 (or so) I taught myself to touch-type in DVORAK, which resolved many ergonomic issues for me.  Long story short: I still love the TypeMatrix keyboards, but I started noticing that my hands and wrists were feeling bad after a long day of typing.  I eventually traced this down to the hand/wrist position: these keyboards require the hands to be fairly close together, although not as close as a typical QWERTY keyboard.

After researching split keyboards for some time, I went out and bought a gently used Ergodox-EZ from eBay.  It worked nicely, and after some adjustment I was able to customize it to do whatever I needed it to do.  However, some issues kept me from using it effectively:

*  Pinky row stagger was nice, but not sufficient; I have quite short pinky fingers, and it was always a reach.
*  Reliance on the "mod" row (below the lower row) for modifiers;  I could have made this different, but these are harder to reach.
*  Hard to reach the "number row" (above the upper row); again with the short fingers thing.
*  Too many keys in the thumb clusters; using the 3 vertically stacked 1U keys is good for some usage, but not great for fast typing (in practice).
*  Increased key travel (compared to the trusty TypeMatrix models) with typical Cherry switches means more work to type *and* more impact on fingers, as I find that I need to really bang the things to get the effective feedback that I need to touch-type with any speed.

Other issues were postural and positional: having the two halves of the Erdogox spaced apart meant that it was possible to put my mouse and mousepad between them; however, I keep finding that I reach outwards (instead of inwards) to find the mouse.  Old habits truly do die hard!

So I kept researching other keyboards, bought a Corne LP kit (from littlekeyboards.com) to try out that approach, and kept researching.  I ran across several interesting layouts, including:

*   Reviung-41 and its variants, which kept both hands together *but* put both halves at an angle, suggesting better posture; and
*   Pteron-56 and its variants, which did much the same thing but had more keys.

However, both of these only supported Cherry-MX key switches, and I felt that using Kailh Choc key switches would give me a typing experience that was closer to the TypeMatrix keyboards (with reduced travel).  I also researched the Hummingbird designs (by PJE66) but decided against using this, as I didn't really want to have to re-learn a new keyboard layout to use this, especially one that relies on chording for any of the alphas or the main punctuation.  (It's not a bad idea in theory, but at this point I'm committed to staying with the DVORAK layout.)

After more research, I found many interesting and worthy designs that offered different strengths and advantages, but none of them quite did what I wanted to do.  So, I installed KiCad, played around with "modding" several of these other layouts (thanks to the design files being available in GitHub; open source hardware design is awesome!), watched numerous videos by Ben Vallack, and then took the leap by deciding to create my own layout.

I would say that this design of mine is "from scratch" but obviously I have been influenced by many other designs.  I'll list most of them here; it's hard to be thorough but these have obviously given me inspiration for various aspects of this design.

*   TypeMatrix EZR-2020 and EZR-2030 (the classics!)
*   Ergodox and its variants, including Ergodox-EZ
*   Corne Choc LP (hot-swap, both V2 from foostan and V3 from Daysgobye)
*   Corne-Xiao (by Lehmanju)
*   Dao-Choc-BLE (by Rafael Yumagulov)
*   Hillside (by mmccoyd; all variants)
*   Hotreus62 (by beekeeb)
*   Humla (by jimmerricks)
*   Hummingbird (by PJE66; unfortunately, no KiCad source is currently available)
*   Iris PE (by keebio; closed source design)
*   Jorne (by Joric)
*   Kyria (by splitkb.com; closed source design)
*   Lily58 (by kata0150)
*   One42 (by Cyril279)
*   Pteron-56 and its variants (by KrakenJokes)
*   Reviung-41 (by gtips) and its variants
*   RevLP (by Cyril279) and RevXLP (by Pete Johanson)
*   VColChoc44 (which integrated an on-board RP2040 MCU)
*   Wren (by Walter Hanley; all variants over time)
*   Zaphod (by Pete Johanson)

One thing to note: I could find no designs that used the Waveshare RP2040-zero module, which was a bit disappointing to me.  So I used this as a vehicle to prove that it could be used in a keyboard design.  There really is a lot to like about this module: it has more IO pins available than the Xiao Seeed RP2040 module, and only takes up less than one square inch of space.  However, this is not a negative statement regarding the Xiao Seeed family, as they look very nice and some others have used them successfully in their own keyboard designs.  At some point I would like to do the same, but IMHO the limited IO pins make it impractical for a single-PCB keyboard with a reasonably useful number of rows and columns, such as this keyboard.  The Waveshare RP2040-zero module addresses these issues handily.

> FYI - I am not sponsored by Waveshare, nor am I receiving compensation in any way.

Finally, a brief note about the name ("BumWings").  I'm not really going to give a deep explanation for that: I come up with silly names for things all the time, and most of them are based on meats or other food items (which makes this an exception).  The words "bum" and "wings" happened to pop into my head and the combination made sense to me at the time, and so I kept it.  It isn't meant to be pejorative or insulting.  If you don't like it, feel free to clone the repo, adapt the design to your needs, and change the name to your liking.  This is what open source hardware design allows you to do.


## Links

https://www.waveshare.com/rp2040-zero.htm


## Components

MCU:     Waveshare RP2040 "zero" (23-pin module with USB-C port) - you can find these on Amazon for a higher price, or on Aliexpress or eBay for a lower price.  They can either be plain, or with pre-soldered pin headers.

Diodes:  D_SOD-123 (you will need 54 of them)

Sockets:  Kailh Choc hot-swap (again, you will need 54 of them)

Key caps:  MBK (either plain, or with legends, at your discretion)

Although the Waveshare RP2040-zero module does have castellated pins and can theoretically be mounted directly to SMD pads, this design doesn't support that.  I figured that I wasn't ready to try this yet (since my soldering skills are barely passable at best) and also the narrow central neck of the keyboard PCB didn't need to be made any smaller, since the module's RP2040 chip is mounted on the underside.  So my decisions were made based on simplicity.  The module does have 20 IO pins that are accessible via the edge pins, so it is possible to mount this similar to a Pro Micro or Elite-C (i.e., with pin headers) and you wouldn't even need to worry about the remaining 9 IO pins on the underside. 

Other resistors/etc:  none

## About the Matrix

The keyboard matrix has 14 columns and 4 rows -- and yes, I know this is not as efficient as it could be...

* Row_up is used for the upper row (above home row)
* Row_home is used for the home row (obviously)
* Row_dn is used for the lower row, plus some thumb cluster keys (1U)
* Row_mod is used for the remaining thumb cluster keys, modifier keys, and the arrow clusters (inverted T)

For columns, X is either L for left hand, or R for right hand.

* Col_Xp2 is the secondary pinky finger alphas, and the lower corner modifier (1.5U outermost).
* Col_Xp1 is the primary pinky finger alphas, and one key from the arrow cluster (outermost).
* Col_Xr is the ring finger alphas, and another key from the arrow cluster (center lower).
* Col_Xm is the middle finger alphas, and another key from the arrow cluster (center upper).
* Col_Xi1 is the primary index finger alphas, and the remaining key from the arrow cluster (innermost).
* Col_Xi2 is the secondary index finger alphas, and the primary thumb key (2U) in the cluster.
* Col_Xt is the innermost 1.5U keys (which will both be Backspaces for me) plus the remaining 2 thumb keys (1.5U and 1U) in the cluster.

On the board, the key switches are labeled as SW0 through SW55.  Note that SW24 and SW28 do not exist; these would have been on Col\_Xt and Row\_up.


## Layout Recommendations

I use DVORAK, so I designed this to work well with DVORAK.  You can adapt this to use Colemak, Colemak-DH, QWERTY (but why?) or any other layout that works best for you.

Here are some other recommendations:

*  The 1.5U keys on the home row (index finger) should be used as Backspaces.  I use two Backspaces, since I "grew up" using TypeMatrix keyboards and the original ones had two backspaces in the middle.  Don't knock it if you haven't tried it, since using alternate Backspaces for each index finger is a great way to get rid of embarrassing typos, especially if your brain is quicker than your fingers and you don't see the typo until a few more characters have been typed.  If this doesn't work for you, then one of them can become a Delete or Return, or you can remap these to whatever works for you.
*  The arrow clusters (remote WASD) would work very well as obvious arrow keys for one side, and navigation keys (Home/End/PgUp/PgDn) for the other side.  You can obviously choose which cluster works better for each use.  The example ZMK configuration shows how these are used for arrows and navigation.
*  The large 2U thumb keys would work as Space and/or Enter, and optional chording modifiers with home-row keys.  Some examples below:
   *  Thumb + index = Ctrl
   *  Thumb + middle = Shift
   *  Thumb + ring = Alt
   *  Thumb + pinky = Win/Super
   *  Thumb + lower corner modifier (1.5U) = Meh
   *  In my example ZMK configuration, both 2U thumb keys are Space.
*  The 1.5U thumb keys would work very well as Delete and Tab, and optional chording modifiers with other keys (see above).
   *  Alternately, these keys can be used for accessing layers (Numbers, Symbols, etc.)
   *  In my example ZMK configuration, the left 1.5U thumb key is a momentary layer key, and the right 1.5U thumb key is either a Return (if tapped) or another layer key (if held).
*  The 1U thumb keys can be used for any purpose, including other modifiers or perhaps MouseKeys (a layer).
   *  In my example ZMK configuration, the left 1U thumb key is the GUI (win/cmd) modifier, and the right 1U thumb key is the Alt modifier.


## Case Options

This repo also contains PCB files for a top plate (with hummingbird art) and a bottom plate (with bigger hummingbird art).  This was heavily inspired by the Corne case.

I'm also working on a metal top plate design.  This could either be full-size, or made in a split (half) version.  The intended case is a wooden board (or "plinth") that can house the PCB and the metal top plate.  My first concept will likely be based on a bamboo cutting board, but I'll need to do the routing myself to hold the PCB, with an inset for the metal top plate so it sits flush with the upper wood surface.  Also, I'll probably need to cut the board at an angle and re-join it along the center line with one side flipped, so it has a chunky "V" shape.  This should hold the metal top plate but I need to confirm this.  I don't have all the woodworking tools to make this happen, but I know some people who do...

Both cases will leave a gap around the RP2040 module.  This can be kept open for visibility, or optionally a cover could be made.  My only cover ideas at this point are either acrylic or solid wood.  The wood cover should have a mini "light-pipe" so the onboard LED can be seen when the cover is installed.  (That way, I can theoretically use the LED to indicate which layer is selected.)


## Firmware Options

ZMK works nicely, as long as you have a fork that is based on Pete Johanson's RP2040 support branch.  I recommend using either of these two forks:

https://github.com/glebsexy/zmk/tree/rp2040-zero-plus-combos-fix
https://github.com/tubbytwins/zmk/tree/rp2040-zero-plus-combos-fix

Much credit goes to Glebsexy for doing the heavy lifting of getting the Waveshare RP2040-zero board added to ZMK!  I went ahead and hacked together my own changes *before* I found that this work was already done, so I've moved over to use their work.

Example ZMK config is here:  https://github.com/tubbytwins/bumwings-zmk-config

QMK also works nicely.  I've set up a fork at the link below with the board definition, as well as some sample layouts.

https://github.com/tubbytwins/qmk_firmware_bumwings/tree/add_bumwings

KMK has not yet been tested, but should work (in theory).


## Wish List and Future Plans

*  Add a Type-C port for expansion options (such as a numpad on the left side)
   *  Figure out how to get I2C working.
   *  Perhaps use an IO expander instead of a separate MCU?  Not trying to save cost here, but a separate MCU seems to be overkill for the job.
   *  Make it hot-swap capable; if it's plugged in, the RP2040 sees it and uses it; if not, it goes along without it.  My spouse is using an old Microsoft Sidewinder (X4?) keyboard that has a detachable numpad, which is a really good idea and *more keyboards* should support this concept.
   *  Type-C seems nice: I really don't want to use TRS or TRRS connectors for this.  However, it seems that very few companies sell "short" (<18 inch) Type-C cables that are known to work.  Keebio is one of the few companies that does, for the Iris keyboard and others.
*  Make a Bluetooth (BLE) version; some of the designs listed above use a module that could work nicely.
   *  Examples:  HolyIOT, Minew, or Waveshare
*  Make a true split version that could be integrated into a single plinth (or wooden board) with a tenting angle.
*  Add an optional display: some companies seem to be making 1.4" rectangular LCDs with rounded corners.  It would be nice to have one of these showing layer info and status in real-time while I type.
*  Make another version that supports the Waveshare RP2040 LCD MCU module, which has a circular LCD screen and looks really cool.

## Feedback

Please feel free to adapt this design to meet your needs, and share your results!  I'm eager to get feedback on how well this keyboard works for others.  If you have any suggestions for improvements **or** alternatives that would make this keyboard more useful, please let me know.


