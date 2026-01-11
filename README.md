# Ender 3 V3 SE Klipper Configuration

This repository contains Klipper configuration files for the Creality Ender 3 V3 SE 3D printer, including:

- printer.cfg
- macros.cfg

## Source & Attribution

These configuration files are based on the guide from [athemis.me](https://athemis.me/projects/klipper_guide/), specifically the 2025 update recommending shubham0x13's config file:

https://athemis.me/projects/klipper_guide/#configuration:~:text=2025%20Update%3A%20I%20recommend%20shubham0x13%E2%80%99s%20config%20file%20that%20has%20several%20upgrades%20compared%20to%20bootuz%E2%80%99s%20config%20file%2E%20Copy%20and%20paste%20the%20contents%20of%20printer%2Ecfg%20and%20macro%2Ecfg%20into%20yours

## Corrections & Improvements

The provided `printer.cfg` corrects build area alignment issues present in the referenced configs. The original configs set prints too far to the left or right, at the edge of the stock Ender 3 V3 SE bed (nominally 235x235mm). However, the actual usable build space is 220x220mm.

<img width="1620" height="1215" alt="image" src="https://github.com/user-attachments/assets/0b2f83c2-f931-450a-b1ad-a5aaa8c1c6dd" />


This configuration shifts the build area as far right as possible, leaving small gaps on the top, right, and bottom edges to ensure reliable homing and print placement.
## Files

- `printer.cfg`: Main Klipper configuration for Ender 3 V3 SE, including pin mappings, stepper settings, bed mesh, BLTouch, fans, heaters, and safety features.
- `macros.cfg`: Custom G-code macros for print start/end, filament loading/unloading, purge routines, PID tuning, and more.

## Usage

1. Flash Klipper firmware to your Ender 3 V3 SE following the [athemis.me guide](https://athemis.me/projects/klipper_guide/).
2. Copy `printer.cfg` and `macros.cfg` from this repository to your Klipper configuration directory.
3. Adjust any settings as needed for your hardware or preferences.
4. Restart Klipper and verify correct homing, bed mesh, and print alignment.

## Notes

- This configuration is tuned for stock hardware. If you have hardware modifications, review and adjust relevant sections.
- For further details, see comments in `printer.cfg` and `macros.cfg`.

### Purge Macros

This configuration uses the `LINE_PURGE` macro in place of `ADAPTIVE_LINE_PURGE`. The `LINE_PURGE` macro draws a purge line along the left edge of the build plate, near or directly on the stock purge illustration. This ensures reliable nozzle priming and is compatible with the shifted build area alignment.

---
For questions or improvements, refer to the upstream guide or open an issue in this repository.
