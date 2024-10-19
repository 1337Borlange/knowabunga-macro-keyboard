# Knowabunga 2024 - macro keyboard 

In this repo you will find QMK keyboard files for the knowabunga keyboard made in Borlänge 2024. As well as all Kicad design files for the PCB itself.

## Building and flashing firmware

To start you are going to need QMK to be setup on the machine. To do this head over to the official guide at [https://docs.qmk.fm/newbs_getting_started](https://docs.qmk.fm/newbs_getting_started).

Once QMK is installed, copy the folder `keyboards/macroblg` into `<qmk_source>/keyboards/`

> Running the following command will print the location of your QMK source directory  
 `qmk env QMK_HOME`

To build the firmware run:
```
qmk compile -kb macroblg -km default
```

This will generate a .bin and .hex file with the firmware. This firmware is designed to work with the Arduino ProMicro which is the controller used on the board.

Once built the firmware can be uploaded. Plug the ProMicro into your computer and run:
```
qmk flash -kb macroblg -km default
```

The on screen instructions will tell you it is waiting for the controller. To put it into programming mode, push once on the reset button located on the board.

If everything worked a progressbar should show up as the firmware is uploaded.

Congratz, you just flashed your first firmware.

## Changing keymap

In the `macroblg/keymaps/default/keymap.c` file you will find the layout specification, this describes what keycodes should be sent for each key. Right now the letters a-h are used (*KC_A - KC_H* respectivly) but you can change these to anything on this list [https://docs.qmk.fm/keycodes](https://docs.qmk.fm/keycodes).

Once changed: save the file, rebuild and reupload using the same instructions as above.,