# ZMK CONFIG FOR THE TOTEM SPLIT KEYBOARD

[TOTEM](https://github.com/GEIGEIGEIST/TOTEM) is a 38 key column-staggered split keyboard running [ZMK](https://zmk.dev/). It is designed for the SEEED XIAO BLE or RP2040.

## HOW TO USE

1. Fork this repo
2. Edit `config/totem.keymap` to customize your layout ([keycodes](https://zmk.dev/docs/codes/))
3. Push to your fork
4. Go to **Actions** tab → select the latest workflow run → download `firmware.zip`
5. Connect left half, press reset twice → drag `totem_left-seeeduino_xiao_ble-zmk.uf2` onto the drive
6. Repeat for right half with `totem_right-seeeduino_xiao_ble-zmk.uf2`

## BOARDS SUPPORTED

- Seeed Studio XIAO BLE (`seeeduino_xiao_ble`)
- Seeed Studio XIAO RP2040 (same shield config, use appropriate board in `build.yaml`)

## BUILDING LOCALLY

```bash
west init -l config
west update
west build -d build/totem_left --board seeeduino_xiao_ble -s app -- -DSHIELD=totem_left
```
