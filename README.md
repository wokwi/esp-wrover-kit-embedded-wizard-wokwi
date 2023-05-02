# Example of integration of Embedded Wizard and Wokwi

## Quick start

```
.\Prepare-Run.ps1
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
- merge binary into single file: `cd build; esptool.py --chip esp32 merge_bin -o merged-flash.bin "@flash_args"`
- open VS Code - Run Wokwi simulation
