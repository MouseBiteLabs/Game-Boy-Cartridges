# MBC5 (Type A, FRAM)

![image](https://github.com/user-attachments/assets/956db129-baf6-4564-b768-96c16d9fd2d5)

## Board Characteristics and Order Information

The zipped folder contains all the gerber files for this board. The following options **must** be chosen when ordering boards for yourself.

- Thickness: 0.8mm
- Layers: 2
- Surface Finish: ENIG
- Gold Fingers: Yes, 30° chamfer

You can use the zipped folder at any board fabricator you like. You may also buy the board from PCBWay using this link (disclosure: I receive 10% of the sale value to go towards future PCB orders of my own):

<a href="https://www.pcbway.com/project/shareproject/Game_Boy_MBC5_Cartridge_Type_A_FRAM_8dda45ae.html"><img src="https://www.pcbway.com/project/img/images/frompcbway-1220.png" alt="PCB from PCBWay" /></a>

**PLEASE NOTE: I have not ordered these from PCBWay, so I cannot attest to their quality or performance. I have put the order details in as I believe they should be, but you need to review all parameters before ordering. Order at your own risk.**

## BOM

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

