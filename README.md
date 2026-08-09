# ZMK-keyboard

Standalone ZMK user config for the nice!nano v2 macro keypad and rotary encoder
project.

## Hardware

- Board: `nice_nano_v2`
- Shield: `nrf52840_arduino_keyboard`
- Rows: D2, D3, D4, D5
- Columns: D6, D7, D8, D9
- Encoder A/B: D10, D11
- Encoder button: D12
- OLED: I2C on P0.26 (SDA) / P0.27 (SCL)
- Matrix: row-to-column diodes

## Build With GitHub Actions

The workflow in `.github/workflows/build.yml` builds the firmware after push.
The normal keyboard build enables the `zmk-usb-logging` snippet for debug logs.
The downloadable artifact is named `firmware-v0.1.<run_number>.zip`.
The OLED uses the built-in ZMK display screen on an SSD1306 128x64 panel.
ZMK Studio support is built with `studio-rpc-usb-uart` and `CONFIG_ZMK_STUDIO=y`.

## Build Locally

With a ZMK/Zephyr toolchain:

```sh
west build -p -b nice_nano_v2 zmk/app -- -DZMK_CONFIG=config -DSHIELD=nrf52840_arduino_keyboard
```

## Flash

For nice!nano v2, use the UF2 bootloader flow:

1. Double-press reset.
2. Copy the generated `.uf2` file to the mounted bootloader drive.
3. Pair the keyboard over Bluetooth.
