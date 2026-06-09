# Game Boy MBC3 Cartridge - Type A, FRAM

# DESIGN IS UNVERIFIED (but probably ok)

This is an alternate design of my <a href="https://github.com/MouseBiteLabs/Game-Boy-Cartridges/tree/main/MBC3%20(Type%20A%2C%20SRAM)">flashable MBC3-based cartridge for the Game Boy</a>. This board uses non-volatile FRAM instead of SRAM to hold save data. I made this specifically for use with the <a href="https://github.com/MouseBiteLabs/Super-Game-Boy-Plus/tree/main">Super Game Boy Plus boards.</a> Even though the board uses FRAM for the save data, the real-time clock data is stored on the MBC3 chip itself, and therefore a battery is included to keep the MBC3 powered on while the Game Boy is off, to keep the time in memory. If the battery dies, your save data will still be available on the FRAM chip, meaning swapping a dead battery to restore clock function will not risk any save data.

**This MBC3 cartridge uses brand new M29F160 EEPROM chips and non-volatile FRAM.**

This circuit board should cover most MBC3 games, and is able to make games up to 2 MB in size, that use up to 256 Kbit of RAM. It is fully compatible with both the <a href="https://www.gbxcart.com/">GBxCart RW</a> and sanni's <a href="https://github.com/sanni/cartreader">Open Source Cart Reader (OSCR)</a> so you can transfer games and save files to and from the board. Because of the FRAM this board utilizes, <a href="https://github.com/MouseBiteLabs/Game-Boy-Cartridges/tree/main/MBC3%20(Type%20A%2C%20SRAM)#why-not-fram">it is technically only fully compatible with regular Game Boy games, and not Game Boy Color games,</a> though no issues have been reported in the past when using them with Game Boy Color games.

![image](https://github.com/user-attachments/assets/5f3d402f-e38b-403d-bb5d-2b4d497336ad)

All gerbers and source files can be found in this repo, as this project is fully open source.

## Important Things Before You Start

1) To use this board, you need to have an original Game Boy game that uses an MBC3 mapper chip. <a href="https://catskull.net/gb-rom-database/">You can find a list of games and their mappers here</a>. Use the search function. Please note the RAM is in bytes, not bits. Since RAM in this repo is defined in bits, you need to convert by multiplying the number of bytes by 8.
2) You will need to remove the MBC3 from your donor cartridge for use on this board. This will require a hot air rework station or a hot plate. There's a list below of other parts you can re-use from the donor cartridge.
3) When soldering parts on, it's a good idea to put kapton tape or otherwise cover the bottom cartridge edge. You do not want to get solder on the cartridge contacts.
4) I am not responsible for any damage you do to your self or your property. Attempt this project at your own risk.
5) I do not guarantee design compatibility. You may encounter issues with certain games. There is also a chance I have made an error in the design or the BOM - if this is the case, I will do everything I can to address the problem as quickly as possible.
6) If you are using this board to make games other than for personal use, you must have permission from the originator to use and distribute any ROM images or other related material. You are responsible for making sure you adhere to any license requirements.

DO NOT use my circuit boards for profiting from stolen work - this especially includes homebrew content, ROM hacks, and using fan-made labels without permission from the originator. **Support original creators!**

## Board Characteristics and Order Information

The zipped folder contains all the gerber files for this board. The following options **must** be chosen when ordering boards for yourself.

- Thickness: 0.8mm
- Surface Finish: ENIG
- Gold Fingers: Yes, 30° chamfer

**I sell this blank circuit board on Etsy, so you don't have to buy a bunch of multiples if you don't want to.** (Click the banner!)

(Not yet available - this is a placeholder.)

<a href="https://mousebitelabs.etsy.com"><img src="https://github-production-user-asset-6210df.s3.amazonaws.com/97127539/239718536-5c9aefe3-0628-4434-b8d8-55ff80ac3bbc.png" alt="PCB from Etsy" /></a>

You can use the zipped folder at any board fabricator you like. You may also buy the board from PCBWay using this link (disclosure: I receive 10% of the sale value to go towards future PCB orders of my own):

<a href="https://www.pcbway.com/project/shareproject/Game_Boy_MBC3_Cartridge_M29F160_FRAM_4735d543.html"><img src="https://www.pcbway.com/project/img/images/frompcbway-1220.png" alt="PCB from PCBWay" /></a>

<a href="https://oshpark.com/shared_projects/Hw9rGuT9">The board is also listed on OSH Park as well.</a> **Be sure to get them in 0.8mm thickness if you order from here.**

## Required Equipment

The EEPROM on the board needs to be programmed somehow. There are a few options for doing this:

1) <a href="https://www.gbxcart.com/">**GBxCart**</a>. This is a perfect option if you want an easy way to make Game Boy cartridges without a lot of extra effort. This is a standalone flasher that plugs into your computer via USB. The cartridge circuit board is fully compatible with it, and it makes reflashing games extremely easy using <a href="https://github.com/lesserkuma/FlashGBX">lesserkuma's FlashGBX software</a>.
2) <a href="https://github.com/sanni/cartreader">**OSCR**</a> by sanni. This is the Open Source Cart Reader, capable of making backups of both the ROM and RAM contents of cartridges across many different systems - like the NES, SNES, Genesis, and of course Game Boy and Game Boy Advance. And you can also use it to flash these Game Boy cartridges. The OSCR however requires assembly (or someone to assemble it for you) and is a bit more cumbersome to interface with on a PC, but it's an extremely powerful tool that I can't recommend enough if you want to expand past Game Boys.
3) At the lowest level, you can buy an EEPROM programmer with a TSOP chip programming adapter. The downside to this method is that you have to desolder the chip every time you want to program it. The <a href="https://flashcatusb.com/">FlashcatUSB</a> is one popular option in retro spaces, but I use the <a href="https://xgecu.myshopify.com/products/xgecu-new-t48-tl866-3gprogrammer-v12-01-support-28000-ics-for-spi-nor-nand-flash-emmc-bga153-162-169-100-221-tsop-sop-plcc">T48 programmer</a> with the <a href="https://xgecu.myshopify.com/products/100-original-xgecu-adp_f48_ex-1-tsop48-special-adapter-for-nor-flash-only-use-on-t48-tl866-3g-programmer">TSOP48 adapter</a>.

### How to Program the Cartridges

<a href="https://github.com/MouseBiteLabs/Game-Boy-Cartridges/wiki">Check out the wiki for more information.</a>

## Battery Safety

When assembling a board, I recommend populating all the parts *except* the battery, and getting it to run initially without it. This is to make it easier to fix any solder connections that might need fixing, without having to worry about getting the battery hot. And if you need to rework anything near the battery after you've put it on the board, be safe and remove it before putting a hot soldering iron next to it.

If you're assembling these boards with a hot plate or hot air, *do not* solder the battery on this way. You should use an iron, and keep heat off of the battery as much as possible. 

(Also check polarity!)

## Board Configurations

The board comes with one set of jumper pads for solder bridges - SJ3.

### MBC3 Type Select (SJ3)

The MBC3 chip you use from the donor cartridge can be one of a few different types:

- If your MBC3 doesn't have a revision letter on it (it just says "MBC3" on it) then bridge the middle pad of SJ3 to the left. (You will also need to populate Q1!)
- If your MBC3 *does* have a revision letter, such as MBC3A or MBC3B, then bridge the middle pad of SJ3 to the right.

![image](https://github.com/user-attachments/assets/6c26547f-eecb-4edb-84ed-a50d2ca8632d)

*[Images of MBC3 chips from <a href="https://gbhwdb.gekkio.fi/cartridges/mbc3.html">Game Boy Hardware Database</a>.]*

### Games Without a Real-Time Clock

If your game does *not* use the RTC function with the crystal X1, then you need to bridge the pads of Z1. You also do not need to populate the battery on the board.

![image](https://github.com/MouseBiteLabs/Game-Boy-MBC3-Cartridge/assets/97127539/d46ea632-6318-4e5d-bf40-c4e9a7f52aa1)

You must also bridge *all three* of the rev pads. You can use a wire to make this easier.

<img width="415" height="280" alt="image" src="https://github.com/user-attachments/assets/01b38dbf-8131-4211-97f6-531c66ecce39" />

## Test Points and Final Checkout

On the back of the board are five test points. Here's where they are connected:

- TP1: MBC3 supply voltage
- TP2: Battery voltage (after R1)
- TP3: Battery voltage (positive terminal of battery)
- TP4: Ground
- TP5: VCC input voltage

After you assemble your game, you should measure the current out of the battery. But first, you should program it with the GBxCart, or if you programmed the EEPROM separately, put it into a Game Boy and cycle power once. Then, flip the PCB upside down on a non-conductive surface (not your leg), and set your multimeter in DC millivolts (or volts). Put the positive probe on TP3 and the negative probe on TP2. If you used a 10kΩ for R1, as indicated in the BOM, you should read a voltage in the tens of millivolts. If you have something much higher, especially voltages above 50mV, then you likely have an issue or short circuit on the board somewhere.

**Note: You need to power up the game at least once before battery currents will make sense - the battery management ICs can start up in an unknown state before applying main power to the board.**

To estimate battery life, see <a href="https://github.com/MouseBiteLabs/Game-Boy-MBC3-Cartridge/tree/main/Technical#estimating-battery-life">this section in the Technical Design Document of my first MBC3 board design</a>, or for more in-depth analysis, <a href="https://hackaday.io/project/11864-tritiled/log/72554-determining-maximum-runtime-176-to-202-years-cr2032">this Hackaday post</a>.

### Current Draw Measurements

When using the real-time clock function of the MBC3, the revision of MBC3 chip you are using will influence the current draw out of the battery when the game is off, and thus how long your battery life will last.

<a href="https://github.com/MouseBiteLabs/Game-Boy-Cartridges/tree/main/MBC3%20(Type%20A%2C%20SRAM)">**The results in this table are taken from my MBC3 SRAM board repository.**</a> Because the FRAM board does not need to keep the RAM powered on, the actual current draws for the FRAM board will be lower than the values in this table. However, it is still a good reference for "ranking" MBC3 chips based on current draw for RTC purposes.

For the test set up, I replaced the battery with a regulated DC power supply set for 3 VDC for consistency, on an MBC3 SRAM cart board with an MM1134 chip for U4, and brand new AS6C62256 SRAM. The "no RTC" measurements have Z1 (or C3) shorted, and the "with RTC" measurements have R2, C2, Z1, and X1 populated. I used a Fluke 117 Multimeter in DC mV mode for measurements.

| Rev   | P/N      | Current draw (without RTC) | Battery Life Estimate (no RTC, CR2025) | Current draw (with RTC) | Battery Life Estimate (RTC, CR2025)  | Battery Life Estimate (RTC, CR2032) |
| ----- | -------- | -------------------------- | -------------------------------------- | ----------------------- | ------------------------------------ | ----------------------------------- |
| MBC3  | LR385364 |          0.2 uA            |               >50 years                |            1.8 uA       |               10 years               |            14 years                 |
| MBC3  | BU3631K  |          0.6 uA            |                31 years                |            1.6 uA       |               12 years               |            16 years                 |
| MBC3  | P-1      |          0.4 uA            |                47 years                |            3.8 uA       |               5 years                |             7 years                 |
| MBC3A | LR38536B |          0.2 uA            |               >50 years                |            1.5 uA       |               13 years               |            18 years                 |
| MBC3A | BU3632K  |          0.5 uA            |                37 years                |            1.5 uA       |               13 years               |            18 years                 |
| MBC3A | P-2      |          0.5 uA            |                37 years                |            3.9 uA       |               5 years                |            7 years                  |
| MBC3B | BU3634K  |          0.6 uA            |                31 years                |            1.5 uA       |               13 years               |            18 years                 |
| MBC3B | P-2      |          0.4 uA            |                47 years                |            3.7 uA       |               5 years                |            7 years                  |

## Board Fitment

The shape of this board was originally meant to mimic original Game Boy circuit boards as closely as possible. Unfortunately, when placed in some aftermarket Game Boy cartridge shells (like those from Cloud Game Store), the circuit board has a lot of freedom to rotate around the main screw hole in the bottom-middle of the cartridge. This can cause misalignment when you put it in a Game Boy, which can cause a game to either not load properly (garbled Game Boy logo) or shut off the Game Boy because of a short circuit. This isn't *dangerous* or anything, just annoying.

In order to make the boards fit nicer in any kind of shell, I added extended tabs of circuit board material to the edges of the cartridges to keep it from rotating too much in shells, which was suggested to me by <a href="https://github.com/orangeglo">orangeglo</a>! (Thanks!)

If you're having trouble fitting the circuit board into a shell, because the tabs interfere with the cart edges, you can safely sand or trim them down as there is no copper within the tabs themselves. The only shell that appears to require any kind of trimming are Kitsch-Bent shells.

## Bill of Materials (BOM)

Your parts list will vary depending on the game you are trying to make, and what chips you have for the battery management (if any). **You cannot use both U4 and U5 - you must choose one or the other.** U4 comes from a donor cartridge, and U5 is a readily available aftermarket option.

Please carefully review the parts you need for the board you are trying to make. Do not add any parts to your build that don't appear in the column for the game you are making. This means you cannot populate every component on the board at the same time.

**NOTE: If you are not using the RTC function of the MBC3, you need to bridge the pads of Z1 (or C3) with solder, and you do not need to include the battery.**

| Reference Designators | Value/Part Number              | Package          | Description        | No RTC         | RTC carts with U4  | RTC carts without U4  | Source                                           |
| --------------------- | ------------------------------ | ---------------- | ------------------ | -------------  | ------------------ | --------------------- | ------------------------------------------------ |
| B1                    | CR2032, CR2025, CR2016         | CR2032           | Backup Battery     |                | x                  | x                     | [https://mou.sr/3SeAzfT](https://mou.sr/3SeAzfT) |
| C19                   | 0.1uF                          | 0603             | Capacitor (MLCC)   | x              | x                  | x                     | [https://mou.sr/3ENc15O](https://mou.sr/3ENc15O) |
| C36                   | 15pF                           | 0603             | Capacitor (MLCC)   |                | x                  | x                     | https://mou.sr/3PPorjO                           |
| Z1                    | 15pF                           | 0603             | Capacitor (MLCC)   |                | x                  | x                     | https://mou.sr/3PPorjO                           |
| C20                   | 0.1uF                          | 0603             | Capacitor (MLCC)   | x              | x                  | x                     | [https://mou.sr/3ENc15O](https://mou.sr/3ENc15O) |
| C21                   | 0.1uF                          | 0603             | Capacitor (MLCC)   | x              | x                  | x                     | [https://mou.sr/3ENc15O](https://mou.sr/3ENc15O) |
| C22                   | 0.1uF                          | 0603             | Capacitor (MLCC)   | x              | x                  | x                     | [https://mou.sr/3ENc15O](https://mou.sr/3ENc15O) |
| C34                   | 0.1uF                          | 0603             | Capacitor (MLCC)   |                | x                  |                       | [https://mou.sr/3ENc15O](https://mou.sr/3ENc15O) |
| C35                   | 0.1uF                          | 0603             | Capacitor (MLCC)   |                |                    | x                     | [https://mou.sr/3ENc15O](https://mou.sr/3ENc15O) |
| Q3                    | 2N7002                         | SOT-23           | N-Channel FET      | If MBC3 no rev | If MBC3 no rev     | x                     | [https://mou.sr/3rgfh6J](https://mou.sr/3rgfh6J) |
| R17                   | 10k                            | 0603             | Resistor           | x              | x                  | x                     | [https://mou.sr/3riR7IH](https://mou.sr/3riR7IH) |
| R29                   | 130k                           | 0603             | Resistor           |                |                    | x                     | [https://mou.sr/3MjXliy](https://mou.sr/3MjXliy) |
| R30                   | 49.9k                          | 0603             | Resistor           |                |                    | x                     | https://mou.sr/3Q3NRZO                           |
| R31                   | 10k                            | 0603             | Resistor           |                | x                  | x                     | [https://mou.sr/3riR7IH](https://mou.sr/3riR7IH) |
| R32                   | 330k                           | 0603             | Resistor           |                | x                  | x                     | [https://mou.sr/3PZ2pvj](https://mou.sr/3PZ2pvj) |
| U7                    | M29F160                        | TSOP-48          | Flash EEPROM       | x              | x                  | x                     | [https://mou.sr/3N0a9eL](https://mou.sr/3N0a9eL) |
| U8                    | MBC3                           | QFP-32           | MBC3 Mapper        | x              | x                  | x                     | Donor MBC3 Game Boy cartridge                    |
| U9                    | FM18W08-SG                     | SOIC-28          | FRAM               | x              | x                  | x                     | [https://mou.sr/4cRIJlb](https://mou.sr/4cRIJlb) |
| U10                   | SN74LVC1G332                   | SOT-363          | 3-input Or Gate    | x              | x                  | x                     | [https://mou.sr/3XdbXoN](https://mou.sr/3XdbXoN) |
| U14                   | MM1026, MM1134, BA6129, BA6735 | SOIC-8           | Battery Management |                | x                  |                       | Donor Game Boy cartridge                         |
| U15                   | TPS3613                        | MSOP-10          | Battery Management |                |                    | x                     | [https://mou.sr/45Ir2kh](https://mou.sr/45Ir2kh) |
| X3                    | 32.768 kHz                     | Radial           | Crystal Oscillator |                | x                  | x                     | https://mou.sr/3ZteKuy                           |

## Labels

If you want a Bucket Mouse branded label for your cartridge, look no further than <a href="https://krizdingus.com/mousebitelabs/">krizdingus's designs</a>. Special thanks to Kris for designing these, they look awesome! (If you are going to order/print these, use the high-res images hosted on his website, and *keep the labels for personal or non-commercial use only.*)

![image](https://github.com/MouseBiteLabs/Game-Boy-MBC3-Cartridge/assets/97127539/cafe3d48-8019-40c0-ab70-6fd012d93657)

## Revision History

### v1.1
- Added pin 1 indicator on silkscreen for U10
- Fixed error where the FRAM and OR gate were powered on the battery (VSW) instead of VCC

### v1.0
- Initial revision

## Resources and Acknowledgements

- <a href="http://www.devrs.com/gb/files/hardware.html">Jeff Frohwein's GameBoy Tech Page</a>
- <a href="https://gbhwdb.gekkio.fi/">Game Boy Hardware Database</a>
- <a href="https://catskull.net/gb-rom-database/">Nintendo Gameboy Game List</a>
- <a href="https://www.gbxcart.com/">insideGadgets discord server for GBxCart RW compatibility requirements</a>
- <a href="https://github.com/lesserkuma/FlashGBX">Lesserkuma's FlashGBX software</a>
- <a href="https://github.com/sanni/cartreader">sanni's Open Source Cart Reader (OSCR)</a>, and thanks to the OSCR discord server for help and feedback
- Board outline modified from <a href="https://tinkerer.us/projects/homebrew-gameboy-cartridge.html">Dillon Nichols's Homebrew Gameboy Cartridge project</a>
- Thanks to <a href="https://github.com/orangeglo">orangeglo</a> for his suggestion of adding spacers around the board edge for better fitment in aftermarket cartridges
- Some components from <a href="https://github.com/adafruit/Adafruit-Eagle-Library">Adafruit's Eagle parts library</a>
- Some components from <a href="https://www.snapeda.com/">SnapMagic</a>
- Thank you to <a href="https://github.com/Gekkio">gekkio</a> for their deep Game Boy knowledge resources, and for collaboration in demystifying some of the design choices on Game Boy cartridges

## License

<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/80x15.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">Creative Commons Attribution-ShareAlike 4.0 International License</a>. You are able to copy and redistribute the material in any medium or format, as well as remix, transform, or build upon the material for any purpose (even commercial) - but you **must** give appropriate credit, provide a link to the license, and indicate if any changes were made.

©MouseBiteLabs 2025
