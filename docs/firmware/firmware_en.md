# Firmware

## Flash the firmware
Download the firmware of VIA from below
- [lskbd_rev1_via.uf2](https://github.com/foostan/kbd_firmware/blob/main/keyboards/lskbd/qmk/qmk_firmware/.build/lskbd_rev1_via.uf2)

Connect to the PC while holding down the BOOT button, or while connected to the PC, hold down the BOOT button and press the RESET button.
After that, an RPI-PR2 device will be mounted.

![btn](https://github.com/foostan/lskbd/assets/736191/91329a6a-8a0d-4d2d-9b1a-3d210b58bd99)

Drop the downloaded uf2 file into the RPI-PR2 device to complete flash.

![flash](https://github.com/foostan/lskbd/assets/736191/8de0f70a-ad3b-46c1-a0dc-98d4f70d812c)


Once the firmware has been written to one side, follow the same procedure for the other side.

## (Optional) If you build the firmware yourself

Refer to [the QMK _getting started_ guide](https://docs.qmk.fm/#/newbs_getting_started),
and install the necessary software according to your OS
(it takes quite some time to install).

Once the environment is ready,
build the firmware for LSKBD with the following files.
https://github.com/foostan/kbd_firmware/tree/main/keyboards/lskbd/qmk/qmk_firmware

## Change your keymap

Please download json file from bellow and load at VIA
- [lskbd](https://github.com/foostan/kbd_firmware/blob/main/keyboards/lskbd/the-via/lskbd.json)

![load_json](https://github.com/foostan/kbd_firmware/assets/736191/67398174-0ef7-4698-9e39-6595b8320428)
![loaded_json](https://github.com/foostan/lskbd/assets/736191/a43ec9c7-5c84-4933-8bc3-a4a6ea5d1ca9)
