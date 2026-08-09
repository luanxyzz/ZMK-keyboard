# nRF52840 ZMK Keyboard

This folder is a standalone ZMK user config for the nice!nano v2 macro keypad
and rotary encoder project.

## Hardware

- Board: `nice_nano_v2`
- Shield: `nrf52840_arduino_keyboard`
- Rows: D2, D3, D4, D5
- Columns: D6, D7, D8, D9
- Encoder A/B: D10, D11
- Encoder button: D12
- Matrix: row-to-column diodes

## Build With GitHub Actions

Use this `ZMK` folder as the root of a `zmk-keyboard` GitHub repository. The
workflow in `.github/workflows/build.yml` will build the firmware after push.

## Build Locally

With a ZMK/Zephyr toolchain:

```sh
west build -p -b nice_nano_v2 zmk/app -- -DSHIELD=nrf52840_arduino_keyboard
```

## Flash

For nice!nano v2, use the UF2 bootloader flow:

1. Double-press reset.
2. Copy the generated `.uf2` file to the mounted bootloader drive.
3. Pair the keyboard over Bluetooth.
