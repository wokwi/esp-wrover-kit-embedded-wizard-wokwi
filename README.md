# Example of integration of Embedded Wizard and Wokwi

## Quick start

```
mkdir build
cd build
Invoke-WebRequest -Uri "https://github.com/georgik/esp-wrover-kit-embedded-wizard-wokwi/releases/download/v0.1/EmbeddedWizard-ESP-WROVER-KIT-merged.bin" -OutFile "EmbeddedWizard-ESP-WROVER-KIT-merged.bin"
```

Open VS Code. Install `Wokwi` extension. CTRL+Shift+P, search for `Request a new license`. Activate Wokwi.

CTRL+Shift+P - `Wokwi - Start Simulation`

## Full build

- install ESP-IDF 5.0.1
- install Embedded Wizard
- install Embedded Wizard SDK for ESP Wrover Kit
- open Brick Game project in Embedded Wizard and Generate code
- open Terminal with activated ESP-IDF, change to directory with Embedded Wizard SDK
- build: `idf.py build`
- merge binary into single file: `cd build; esptool.py --chip esp32 merge_bin -o EmbeddedWizard-ESP-WROVER-KIT-merged.bin "@flash_args"`
- open VS Code - Run Wokwi simulation

## Flashing to real HW

```
esptool.py --chip esp32 -p COM10 -b 926100 write_flash 0x0 build/EmbeddedWizard-ESP-WROVER-KIT-merged.bin
```