# Game Boy MBC5 Cartridge - Type A, FRAM

This is an alternate design of my <a href="https://github.com/MouseBiteLabs/Game-Boy-Cartridges/tree/main/MBC5%20(Type%20A%2C%20SRAM)">flashable MBC5-based cartridge for the Game Boy</a>. This board uses non-volatile FRAM instead of SRAM to hold save data. I made this specifically for use with the <a href="https://github.com/MouseBiteLabs/Super-Game-Boy-Plus/tree/main">Super Game Boy Plus boards.</a>

**This MBC5 cartridge uses brand new M29F160 EEPROM chips and non-volatile FRAM.**

This circuit board should cover most MBC5 games, and is able to make games up to 2 MB in size, that use up to 256 Kbit of RAM. It is fully compatible with both the <a href="https://www.gbxcart.com/">GBxCart RW</a> and sanni's <a href="https://github.com/sanni/cartreader">Open Source Cart Reader (OSCR)</a> so you can transfer games and save files to and from the board. Because of the FRAM this board utilizes, <a href="https://github.com/MouseBiteLabs/Game-Boy-Cartridges/tree/main/MBC5%20(Type%20A%2C%20SRAM)#why-not-fram">it is technically only fully compatible with regular Game Boy games, and not Game Boy Color games,</a> though no issues have been reported in the past when using them with Game Boy Color games.

![image](https://github.com/user-attachments/assets/a93cc2a2-a764-492f-917b-0d4da244b6f1)

All gerbers and source files can be found in this repo, as this project is fully open source.

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

<a href="https://www.pcbway.com/project/shareproject/Game_Boy_MBC5_Cartridge_Type_A_FRAM_8dda45ae.html"><img src="https://www.pcbway.com/project/img/images/frompcbway-1220.png" alt="PCB from PCBWay" /></a>

<a href="https://oshpark.com/shared_projects/4iVMHuUe">The board is also listed on OSH Park as well.</a> **Be sure to get them in 0.8mm thickness if you order from here.**

## Required Equipment

The EEPROM on the board needs to be programmed somehow. There are a few options for doing this:

1) <a href="https://www.gbxcart.com/">**GBxCart**</a>. This is a perfect option if you want an easy way to make Game Boy cartridges without a lot of extra effort. This is a standalone flasher that plugs into your computer via USB. The cartridge circuit board is fully compatible with it, and it makes reflashing games extremely easy using <a href="https://github.com/lesserkuma/FlashGBX">lesserkuma's FlashGBX software</a>.
2) <a href="https://github.com/sanni/cartreader">**OSCR**</a> by sanni. This is the Open Source Cart Reader, capable of making backups of both the ROM and RAM contents of cartridges across many different systems - like the NES, SNES, Genesis, and of course Game Boy and Game Boy Advance. And you can also use it to flash these Game Boy cartridges. The OSCR however requires assembly (or someone to assemble it for you) and is a bit more cumbersome to interface with on a PC, but it's an extremely powerful tool that I can't recommend enough if you want to expand past Game Boys.
3) At the lowest level, you can buy an EEPROM programmer with a TSOP chip programming adapter. The downside to this method is that you have to desolder the chip every time you want to program it. The <a href="https://flashcatusb.com/">FlashcatUSB</a> is one popular option in retro spaces, but I use the <a href="https://xgecu.myshopify.com/products/xgecu-new-t48-tl866-3gprogrammer-v12-01-support-28000-ics-for-spi-nor-nand-flash-emmc-bga153-162-169-100-221-tsop-sop-plcc">T48 programmer</a> with the <a href="https://xgecu.myshopify.com/products/100-original-xgecu-adp_f48_ex-1-tsop48-special-adapter-for-nor-flash-only-use-on-t48-tl866-3g-programmer">TSOP48 adapter</a>.

### How to Program the Cartridges

<a href="https://github.com/MouseBiteLabs/Game-Boy-Cartridges/wiki">Check out the wiki for more information.</a>

## Board Fitment

The shape of this board was originally meant to mimic original Game Boy circuit boards as closely as possible. Unfortunately, when placed in some aftermarket Game Boy cartridge shells (like those from Cloud Game Store), the circuit board has a lot of freedom to rotate around the main screw hole in the bottom-middle of the cartridge. This can cause misalignment when you put it in a Game Boy, which can cause a game to either not load properly (garbled Game Boy logo) or shut off the Game Boy because of a short circuit. This isn't *dangerous* or anything, just annoying.

In order to make the boards fit nicer in any kind of shell, I added extended tabs of circuit board material to the edges of the cartridges to keep it from rotating too much in shells, which was suggested to me by <a href="https://github.com/orangeglo">orangeglo</a>! (Thanks!)

If you're having trouble fitting the circuit board into a shell, because the tabs interfere with the cart edges, you can safely sand or trim them down as there is no copper within the tabs themselves. The only shell that appears to require any kind of trimming are Kitsch-Bent shells.

## Bill of Materials (BOM)

| Reference | Value/Part Number | Package | Description      | Source                                           |
| --------- | ----------------- | ------- | ---------------- | ------------------------------------------------ |
| C19       | 0.1u              | 0603    | Capacitor (MLCC) | [https://mou.sr/3ENc15O](https://mou.sr/3ENc15O) |
| C20       | 0.1u              | 0603    | Capacitor (MLCC) | [https://mou.sr/3ENc15O](https://mou.sr/3ENc15O) |
| C21       | 0.1u              | 0603    | Capacitor (MLCC) | [https://mou.sr/3ENc15O](https://mou.sr/3ENc15O) |
| C22       | 0.1u              | 0603    | Capacitor (MLCC) | [https://mou.sr/3ENc15O](https://mou.sr/3ENc15O) |
| R17       | 10k               | 0603    | Resistor         | [https://mou.sr/3riR7IH](https://mou.sr/3riR7IH) |
| U7        | M29F160           | TSOP-48 | Flash EEPROM     | [https://mou.sr/3MNWQ0b](https://mou.sr/3MNWQ0b) |
| U8        | MBC5              | QFP-32  | MBC5 Mapper      | Donor Game Boy Game                              |
| U9        | FM18W08-SG        | SOIC-28 | FRAM             | [https://mou.sr/4cRIJlb](https://mou.sr/4cRIJlb) |
| U10       | SN74LVC1G332      | SOT-363 | 3-input Or Gate  | [https://mou.sr/3XdbXoN](https://mou.sr/3XdbXoN) |

## Labels

If you want a Bucket Mouse branded label for your cartridge, look no further than <a href="https://krizdingus.com/mousebitelabs/">krizdingus's designs</a>. Special thanks to Kris for designing these, they look awesome! (If you are going to order/print these, use the high-res images hosted on his website, and *keep the labels for personal or non-commercial use only.*)

![image](https://github.com/MouseBiteLabs/Game-Boy-MBC5-Cartridge/assets/97127539/6ff3c8ef-356c-4162-9782-bd76befa0928)

## Revision History

### v1.1
- Fix board number and update silkscreen for consistency

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
