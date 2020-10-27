# Quefrency Rev2

## How to flash firmware

1. Install `qmk`
    - Make sure to install `avr-gcc avrdude avr-libc arm-none-eabi-binutils arm-none-eabi-gcc` if you're on Arch/Manjaro
2. Configure layout using [QMK Configurator](https://config.qmk.fm/#/keebio/quefrency/rev2/LAYOUT_65_with_macro) or by editing the default layout (`keymap.c` in `qmk_firmware/keyboards/keebio/quefrency/keymaps/default65macro`
3. Make a new folder in `qmk_firmware/keyboards/keebio/quefrency/keymaps/` with whatever name you want to use for the keymap (e.g. `foo`)
4. Move the keymap config you made to this new folder and name it `keymap.c`
    - If you used the QMK Configurator, download the JSON file and use the command `qmk json2c -o keymap.c keymap.json` to convert it to a C file
5. Individually plug in both halves of the keyboard, and press the reset button on both halves (on the bottom side of the PCBs)
6. Run the command `sudo make keebio/quefrency/rev2:foo:dfu` in the `qmk_firmware` folder **twice** (one for each half of the keyboard) to flash the firmware
