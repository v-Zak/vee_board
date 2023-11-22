# ErgoBoard

A personalised keyboard clone of a [Josukey](https://github.com/Narkoleptika/josukey) which is based off a corne. This version is Diodless and Wireless only.

The board was created using the below method.

# Initial Layout

## [ErgoPad](https://github.com/pashutk/ergopad)
Use Ergopad to get a rough layout of one of the halves using a tablet.

## [Ergogen](https://github.com/ergogen/ergogen)
Use Ergogen to recreate the layout using the online tool first for the live viewer.

# [Josukey Fork](https://github.com/Narkoleptika/josukey)
Use Josukey NPM as it includes the footprints for the nano etc. Follow the installation instructions below.

## Prerequisites
* Node
* Docker
* Kicad
  
## Getting Started

### Installation

Get my files on your computer and install dependencies.

```bash
git clone https://github.com/v-Zak/ergoboard.git
cd ergoboard
npm i
```

## Ergogen

### Build

This will run Ergogen and build all of the output files. 
https
```bash
npm run ergogen:build
```

This will overwrite the output folder so once happy with the pcb move to kicad folder before routing.

### Watch

This will watch the `config.yaml` file and the `footprints` directory and run the build command whenever there are changes.

```bash
npm run ergogen:watch
```

Same story so move to kicad folder

## Routing

Route all the nets within kicad and then export to a gerber file refer to [this video](https://youtu.be/M_VuXVErD6E?si=WyvUVawYogwmqlh6) for help

Use plot to create gerber files, once routed and then order off a pcb website by uploading the gerber.zip

## Order Parts 

The parts list (for the v_zak keyboard) needed is as follows:

| Name                                 | Quantity | Link                                                                                                                       | Cost ($) |
|--------------------------------------|----------|----------------------------------------------------------------------------------------------------------------------------|----------|
| PCB (Use Gerber)                     | 2        | JLPCB or PCBWay                                                                                                            | 12.93    |
| JST 2.0 PH Female                    | 2        | [aliexpress](https://www.aliexpress.com/item/33009614944.html?spm=a2g0o.order_list.order_list_main.5.761818026oXKZu)       | 1.70     |
| 3x6 Micro Switch                     | 2        | [aliexpress](https://www.aliexpress.com/item/4000700060759.html?spm=a2g0o.order_list.order_list_main.11.761818026oXKZu)    | 2.96     |
| 7 pin 3mm & 1.5mm gap Slide Switch   | 2        | [aliexpress](https://www.aliexpress.com/item/1005003829889015.html?spm=a2g0o.order_list.order_list_main.16.761818026oXKZu) | 2.82     |
| ProMicro NRF52840 (Nice! Nano Clone) | 2        | [aliexpress](https://www.aliexpress.com/item/1005006074191337.html?spm=a2g0o.order_list.order_list_main.28.761818026oXKZu) | 16.74    |
| 1u Choc PBT Keycaps                  | 36       | [aliexpress](https://www.aliexpress.com/item/1005004558099208.html?spm=a2g0o.order_list.order_list_main.33.761818026oXKZu) | 27.00    |
| Kalih Choc Red Keycaps               | 36       | [aliexpress](https://www.aliexpress.com/item/1005005066585322.html?spm=a2g0o.order_list.order_list_main.21.761818026oXKZu) | 20.00    |

The total as of 11/11/23 is: 84

## Build guide

refer to [corne](https://github.com/foostan/crkbd) build guides and ignore the diodes. 

## ZMK

refer to [zmk-config repo](https://github.com/v-Zak/zmk-config).

Automatically builds the .uf2 files for flashing using the configs in the config folder.

To change the hardware / board pinouts go into the shields folder and change the files to suit gpio pins etc.

To change keymap and software settings just use the .conf and .keymap files in the config folder.

## Flash 

Drop the uf2 files found in the actions section in github into the folder that appears when the keyboard is connected to the computer. Make sure the left is flashed to the left and the right to the right.

Now test it out!

## Thanks
* <a href="https://github.com/Narkoleptika/josukey" target="_blank">Josukey</a>
* <a href="https://github.com/benvallack/ergogen" target="_blank">BenVallack</a>
* <a href="https://github.com/ergogen/ergogen" target="_blank">Ergogen</a>
* <a href="https://discord.gg/nbKcAZB" target="_blank">Absolem Club Discord</a>
* <a href="https://github.com/tsteffek/Ergogen-V4-Migration-Guide" target="_blank">V4 Migration Guide</a>
* <a href="https://gitlab.com/Audijo/keyboard" target="_blank">Claw</a>
* <a href="https://github.com/MrCarney/mrkeyboard" target="_blank">MrKeyboard</a>
* <a href="https://github.com/foostan/crkbd" target="_blank">Corne keyboard</a>
* <a href="https://github.com/zmkfirmware/zmk" target="_blank">ZMK</a>
* <a href="https://github.com/manna-harbour/miryoku_zmk" target="_blank">Miryoku ZMK</a>