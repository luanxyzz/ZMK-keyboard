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
- Matrix: row-to-column diodes

## Build With GitHub Actions

The workflow in `.github/workflows/build.yml` builds the firmware after push.
The downloadable artifact is named `firmware-v0.1.<run_number>.zip`.

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
