# Game Boy MBC5 Cartridge - Type A, SRAM

This is an updated design of my flashable MBC5-based cartridge for the Game Boy. The MBC5 mapper greatly augments the memory access of the Game Boy for larger games. Most of the games that came out in the last years of the Game Boy and Game Boy Color used the MBC5 mapper.

**This MBC5 cartridge uses brand new M29F160 EEPROM chips and battery-backed SRAM.**

This circuit board should cover most MBC5 games. The features are as follows:

- Able to make games up to 2 MB in size, that use up to 1 Mbit of RAM
- Compatibility with all four of the popular Game Boy battery management ICs - MM1026, MM1134, BA6129, and BA6735
- The option to add battery backup to the cartridge *without* the need of the original battery management ICs - perfect for MBC5 donors that didn't have batteries in them
- Fully compatible with both the <a href="https://www.gbxcart.com/">GBxCart RW</a> and sanni's <a href="https://github.com/sanni/cartreader">Open Source Cart Reader (OSCR)</a> so you can transfer games and save files to and from the board

![image](https://github.com/user-attachments/assets/1934c741-f0d4-4c66-a43a-8c9aae064ad6)

All gerbers and source files can be found in this repo, as this project is fully open source **with attribution.**

## Important Things Before You Start

1) To use this board, you need to have an original Game Boy game that uses an MBC5 mapper chip. <a href="https://catskull.net/gb-rom-database/">You can find a list of games and their mappers here</a>. Use the search function. Please note the RAM is in bytes, not bits. Since RAM in this repo is defined in bits, you need to convert by multiplying the number of bytes by 8.
2) You will need to remove the MBC5 from your donor cartridge for use on this board. This will require a hot air rework station or a hot plate. There's a list below of other parts you can re-use from the donor cartridge.
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

You can use the zipped folder at any board fabricator you like. You may also buy the board from PCBWay using this link (disclosure: I receive 10% of the sale value to go towards future PCB orders of my own):

<a href="https://www.pcbway.com/project/shareproject/Game_Boy_MBC5_Cartridge_M29F160_SRAM_85a95874.html"><img src="https://www.pcbway.com/project/img/images/frompcbway-1220.png" alt="PCB from PCBWay" /></a>

<a href="https://oshpark.com/shared_projects/Gdh9uAeD">The board is also listed on OSH Park as well.</a> **Be sure to get them in 0.8mm thickness if you order from here.**

### Purchase from My Website

You can purchase this circuit board at my website, [https://mousebitelabs.store](https://mousebitelabs.store). Click the following image to be directed to the specific item listing:

<a href="https://mousebitelabs.store/products/game-boy-mbc5-flash-cartridge-circuit-board"><img width="1070" height="182" alt="PCB from MouseBiteLabs" src="https://github.com/user-attachments/assets/14072b8c-4d47-434b-9c31-6d4ec74a28bc" /></a>

### Purchase from Etsy

I also offer the board on Etsy, if you would rather purchase through there - click the banner to be redirected.

<a href="https://mousebitelabs.etsy.com/listing/1894341187/game-boy-cartridge-pcb-mbc5-type-a"><img src="https://github-production-user-asset-6210df.s3.amazonaws.com/97127539/239718536-5c9aefe3-0628-4434-b8d8-55ff80ac3bbc.png" alt="PCB from Etsy" /></a> 

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

The board comes with three sets of jumper pads for solder bridges. SJ1 and SJ2 require you to solder bridge the middle pad either to the left or right pads. SJ3 is configured by either leaving the pads unsoldered or bridging them with solder. Here are the situations where you need to add solder bridges.

**<a href="https://github.com/MouseBiteLabs/Game-Boy-Cartridges/wiki/MBC5">You can check out the wiki for some pictures of boards in various configurations to follow along with.</a>**

### RAM Size Selection (SJ1 and SJ2, or SW1)

These jumpers are located underneath the MBC5 chip, and labeled "64K" and "256K/1M". Solder them to configure the amount of RAM your cart uses. You must configure these pads for every game you make, unless you do not need RAM. <a href="https://catskull.net/gb-rom-database/">You can find a list of games here with their respective RAM sizes.</a>

- If the game you're making uses 256 Kbit or 1 Mbit of RAM, then solder the middle pads of the two jumper sets to the right pads.
- If the game you're making uses 64 Kbit of RAM, then solder the middle pads of the two jumper sets to the left pads.
- SJ1 and SJ2 must be soldered in the same direction.
- The footprint of these selection pads should allow for a DPDT switch, part number CAS-220A1, to be placed on these pads instead of having to bridge the pads with solder.

![image](https://github.com/MouseBiteLabs/Game-Boy-MBC5-Cartridge/assets/97127539/7f242900-f838-4d12-a51a-a679254fe769)

Note that you can make games that only require 64 Kbit of RAM and still use a 256 Kbit or 1 Mbit SRAM chip. You still need to configure the jumpers to the 64Kb setting, though.

**I recommend using 64 Kbit or 256 Kbit RAM chips, unless you absolutely need 1 Mbit for the game you are making.**

### Using an MM1134 or BA6735 for U4 (SJ3)

Bridge the jumper SJ3 if you have either an MM1134 or BA6735 for U4, specifically. Any other battery management IC must leave SJ3 unsoldered.

## Test Points and Final Checkout

On the back of the board are five test points. Here's where they are connected:

- TP1: SRAM supply voltage
- TP2: Battery voltage (after R1)
- TP3: Battery voltage (positive terminal of battery)
- TP4: Ground
- TP5: VCC input voltage

After you assemble your game, you should measure the current out of the battery. But first, you should program it with the GBxCart or the OSCR, or if you programmed the EEPROM separately, put it into a Game Boy and cycle power once. Then, flip the PCB upside down on a non-conductive surface (not your leg), and set your multimeter in DC millivolts (or volts). Put the positive probe on TP3 and the negative probe on TP2. If you used a 10kΩ for R1, as indicated in the BOM, you should read a voltage in the single of millivolts. If you have something much higher, especially voltages above 20mV, then you likely have an issue or short circuit on the board somewhere.

**Note: You need to power up the game at least once before battery currents will make sense - the battery management ICs can start up in an unknown state before applying main power to the board.**

To estimate battery life, see <a href="https://github.com/MouseBiteLabs/Game-Boy-MBC5-Cartridge/tree/main/Technical#estimating-battery-life">this section in the Technical Design Document of my first MBC5 design</a>, or for more in-depth analysis, <a href="https://hackaday.io/project/11864-tritiled/log/72554-determining-maximum-runtime-176-to-202-years-cr2032">this Hackaday post</a>.

## Board Fitment

The shape of this board was originally meant to mimic original Game Boy circuit boards as closely as possible. Unfortunately, when placed in some aftermarket Game Boy cartridge shells (like those from Cloud Game Store), the circuit board has a lot of freedom to rotate around the main screw hole in the bottom-middle of the cartridge. This can cause misalignment when you put it in a Game Boy, which can cause a game to either not load properly (garbled Game Boy logo) or shut off the Game Boy because of a short circuit. This isn't *dangerous* or anything, just annoying.

In order to make the boards fit nicer in any kind of shell, I added extended tabs of circuit board material to the edges of the cartridges to keep it from rotating too much in shells, which was suggested to me by <a href="https://github.com/orangeglo">orangeglo</a>! (Thanks!)

If you're having trouble fitting the circuit board into a shell, because the tabs interfere with the cart edges, you can safely sand or trim them down as there is no copper within the tabs themselves. The only shell that appears to require any kind of trimming are Kitsch-Bent shells.

## Bill of Materials (BOM)

Your parts list will vary depending on the game you are trying to make, and what chips you have for the battery management (if any). **You cannot use both U4 and U5 - you must choose one or the other.** U4 comes from a donor cartridge, and U5 is a readily available aftermarket option.

Please carefully review the parts you need for the board you are trying to make. Do not add any parts to your build that don't appear in the column for the game you are making. This means you *cannot* populate every component on the board at the same time.


| Reference Designators | Value/Part Number              | Package          | Description        | No save carts | Save carts with MM1134 or BA6735 | Save carts with MM1026 or BA6129 | Save carts without donor U4 chip | Source                                           |
| --------------------- | ------------------------------ | ---------------- | ------------------ | ------------- | -------------------------------- | -------------------------------- | -------------------------------- | ------------------------------------------------ |
| B1                    | CR2032, CR2025, CR2016         | CR2032           | Backup Battery     |               | X                                | X                                | X                                | [https://mou.sr/3SeAzfT](https://mou.sr/3SeAzfT) |
| C1                    | 0.1uF                          | 0603             | Capacitor (MLCC)   | X             | X                                | X                                | X                                | [https://mou.sr/3ENc15O](https://mou.sr/3ENc15O) |
| C4                    | 0.1uF                          | 0603             | Capacitor (MLCC)   | X             | X                                | x                                |                                  | [https://mou.sr/3ENc15O](https://mou.sr/3ENc15O) |
| C5                    | 0.1uF                          | 0603             | Capacitor (MLCC)   |               | X                                | X                                | X                                | [https://mou.sr/3ENc15O](https://mou.sr/3ENc15O) |
| C6                    | 10uF                           | 0603             | Capacitor (MLCC)   |               | X                                | X                                | X                                | [https://mou.sr/3mZtSkF](https://mou.sr/3mZtSkF) |
| C7                    | 0.1uF                          | 0603             | Capacitor (MLCC)   | X             | X                                | X                                | X                                | [https://mou.sr/3ENc15O](https://mou.sr/3ENc15O) |
| C8                    | 0.1uF                          | 0603             | Capacitor (MLCC)   |               |                                  |                                  | X                                | [https://mou.sr/3ENc15O](https://mou.sr/3ENc15O) |
| Q1                    | 2N7002                         | SOT-23           | N-Channel FET      |               |                                  |                                  | X                                | [https://mou.sr/3rgfh6J](https://mou.sr/3rgfh6J) |
| Q2                    | 2N7002                         | SOT-23           | N-Channel FET      |               |                                  | X                                |                                  | [https://mou.sr/3rgfh6J](https://mou.sr/3rgfh6J) |
| R1                    | 10k                            | 0603             | Resistor           |               | X                                | X                                | X                                | [https://mou.sr/3riR7IH](https://mou.sr/3riR7IH) |
| R7                    | 10k                            | 0603             | Resistor           |               |                                  | X                                |                                  | [https://mou.sr/3riR7IH](https://mou.sr/3riR7IH) |
| R9                    | 130k                           | 0603             | Resistor           |               |                                  |                                  | X                                | [https://mou.sr/3MjXliy](https://mou.sr/3MjXliy) |
| R10                   | 49.9k                          | 0603             | Resistor           |               |                                  |                                  | X                                | [https://mou.sr/3Q3NRZO](https://mou.sr/3Q3NRZO) |
| U1                    | M29F160                        | TSOP-48          | Flash EEPROM       | X             | X                                | X                                | X                                | [https://mou.sr/3N0a9eL](https://mou.sr/3N0a9eL) |
| U2                    | MBC5                           | QFP-32           | MBC5 Mapper        | X             | X                                | X                                | X                                | Donor MBC5 Game Boy cartridge                    |
| U3                    | AS6C6264, AS6C62256, AS6C1008  | SOP-28, SOP-32   | SRAM               |               | X                                | X                                | X                                | [https://mou.sr/3ZxG6jd](https://mou.sr/3ZxG6jd) |
| U4                    | MM1026, MM1134, BA6129, BA6735 | SOIC-8           | Battery Management |               | X                                | X                                |                                  | Donor Game Boy cartridge                         |
| U5                    | TPS3613                        | MSOP-10          | Battery Management |               |                                  |                                  | X                                | [https://mou.sr/45Ir2kh](https://mou.sr/45Ir2kh) |

*Note that C9 - C11 footprints are only included on the board for strange edge cases that may require them sometime in the future; do not populate! See the technical design document for more information.*

### Usable Donor Cartridge Parts

You can use a few parts from the donor cart on the new board to save some money. Note that you will generally get better reliability with new parts as opposed to old ones. For example: I have seen failed RAM chips from donors in the past.

1) **U2: MBC5** - This one is required
2) **U3: SRAM** - You can use this part *only if* the game you're making uses the same or less amount of RAM that the donor cartridge does
3) **U4: Battery Management IC** - Using this is probably preferred over the TPS3613 because it'll save you money and parts to put on

You could probably transfer over most of the 0.1uF capacitors but they're pretty cheap anyway, so I generally just recommend buying new resistors and capacitors.

## Things to Remember

- The footprint for the battery can fit a CR2032, CR2025, or CR2016 with solder tabs. The only difference is the mAh capacity (larger number = longer life). If you get Panasonic tabbed batteries, you may have to trim the battery tabs to make them fit on the footprint.
  - For untabbed coin cells, you can find battery retainer adapters online, <a href="https://retrogamerepairshop.com/products/hdr-game-boy-game-battery-retainer?variant=40511013290156">like this one</a>.
- For battery management, use either U4 *or* U5 and supporting components. **Do not** use U4 and U5 simultaneously on one board. They will interfere with each other.
- Generally, ROM sizes are conveyed in terms of kilo**bytes** and mega**bytes** (KB, MB). RAM size is usually conveyed in terms of kilo**bits** or mega**bits** (Kbit, Mbit). You can convert Kbit and Mbit to KB and MB by dividing Kbit or Mbit by 8. For example, 256 Kbit = 32 KB.
- You only need to provide ROM and RAM chips that have at least *or greater* the size of the game you are trying to make. That means you can use a 256 Kbit SRAM chip for a game that only requires 64 Kbit of RAM!

## Labels

If you want a Bucket Mouse branded label for your cartridge, look no further than <a href="https://krizdingus.com/mousebitelabs/">krizdingus's designs</a>. Special thanks to Kris for designing these, they look awesome! (If you are going to order/print these, use the high-res images hosted on his website, and *keep the labels for personal or non-commercial use only.*)

![image](https://github.com/MouseBiteLabs/Game-Boy-MBC5-Cartridge/assets/97127539/6ff3c8ef-356c-4162-9782-bd76befa0928)

## Why Not FRAM?

This particular board is designed for using low retention power SRAM, or Static RAM. One downside to SRAM is that you need a battery to keep the SRAM powered on even when the game is turned off if you want to retain the data on the chip. So eventually the battery will die, and your save data will be lost.

The other popular option for holding save data is using FRAM, or Ferroelectric RAM, to keep save data around even after the battery dies (specifically, the popular part that's used for Game Boy FRAM carts is the FM18W08).

So, why would anyone ever use SRAM over FRAM if FRAM doesn't need a battery? Well, they do come with a number of downsides:

1) Quality, new stock, 5V tolerant FRAM is expensive ($12+ per part at the time of writing).
2) Cheaper FRAM chips from eBay or Aliexpress are notoriously flaky (anecdotally, ~50% success rate).
3) FRAM memory access requires different chip select timing than SRAM, and the Game Boy expects SRAM, so it is not natively compatible with FRAM carts. The Gameboy Color specifically cannot (easily) be made to properly access FM18W08 chip. You *can* use an OR gate and add the CLK on the cart edge to try to achieve the necessary timing, but it only works (properly) for DMG/MGB/SGB, not the GBC. It usually *works* in practice for GBC, but it's technically a datasheet violation and can potentially cause issues in edge cases. <a href="https://github.com/Gekkio">(Thanks to gekkio for pointing this out!)</a>

In contrast, *brand new* quality SRAM chips are ~$3, and you can even save that by using the original SRAM from a donor cartridge if you want to. You will *easily* get more than a decade of life running on a battery. You're already assembling this cartridge; you can dump the save and replace the battery before then.

<a href="https://github.com/MouseBiteLabs/Game-Boy-Cartridges/tree/main/MBC5%20(Type%20A%2C%20FRAM)">I do have an FRAM-enabled version of this cartridge,</a> if you're so inclined. They definitely have their place and their benefits. But I personally prefer the SRAM design because I refuse to use AliExpress FRAM chips, and don't want to add a big cost with new FRAM.

## Revision History

### v1.2
- Fix board number

### v1.1
- Update silkscreen style to match other boards
- Add board number to board copper

### v1.0
- Initial revision

## Resources and Acknowledgements

- <a href="http://www.devrs.com/gb/files/hardware.html">Jeff Frohwein's GameBoy Tech Page</a>
- <a href="https://gbhwdb.gekkio.fi/">Game Boy Hardware Database</a>
- <a href="https://catskull.net/gb-rom-database/">Nintendo Gameboy Game List</a>
- <a href="https://www.gbxcart.com/">insideGadgets discord server for GBxCart RW compatibility requirements</a>
- <a href="https://github.com/lesserkuma/FlashGBX">Lesserkuma's FlashGBX software</a>
- <a href="https://github.com/sanni/cartreader">sanni's Open Source Cart Reader (OSCR)</a>, and thanks to the OSCR discord server for help and feedback
- <a href="https://www.alldatasheet.com/datasheet-pdf/pdf/99104/MITSUBISHI/MM1026.html">System Reset IC Datasheet</a>
- <a href="https://www.ti.com/lit/ds/symlink/tps3613-01.pdf?HQS=dis-mous-null-mousermode-dsf-pf-null-wwe&ts=1698238885366&ref_url=https%253A%252F%252Feu.mouser.com%252F">TPS3613 Datasheet</a>
- Board outline modified from <a href="https://tinkerer.us/projects/homebrew-gameboy-cartridge.html">Dillon Nichols's Homebrew Gameboy Cartridge project</a>
- Thanks to <a href="https://github.com/orangeglo">orangeglo</a> for his suggestion of adding spacers around the board edge for better fitment in aftermarket cartridges
- Some components from <a href="https://github.com/adafruit/Adafruit-Eagle-Library">Adafruit's Eagle parts library</a>
- Some components from <a href="https://www.snapeda.com/">SnapMagic</a>
- Thank you to <a href="https://github.com/Gekkio">gekkio</a> for their deep Game Boy knowledge resources, and for collaboration in demystifying some of the design choices on Game Boy cartridges

## License

<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/80x15.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">Creative Commons Attribution-ShareAlike 4.0 International License</a>. You are able to copy and redistribute the material in any medium or format, as well as remix, transform, or build upon the material for any purpose (even commercial) - but you **must** give appropriate credit, provide a link to the license, and indicate if any changes were made.

©MouseBiteLabs 2025
