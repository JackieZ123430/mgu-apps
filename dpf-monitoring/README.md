# DPF Monitoring

The diesel particulate filter of a BMW diesel on the iDrive 7 (MGU) head unit, in the look of BMW's own screens: soot and ash load, regenerations (live, interrupted, history), differential pressure and exhaust temperatures, read from the diesel engine unit (DDE) with UDS `0x22` ReadDataByIdentifier only. Nothing is ever written to the car.

- **Overview:** soot load and exhaust temperature as bars, a drawing of the filter with soot, ash, heat and the pressure difference, and the status (filter OK / regeneration due / running).
- **Live data:** soot, pressure difference and both exhaust temperatures with their last 5 minutes; every other value as a list, with the raw replies on request.
- **History:** the regenerations the app has watched and the intervals from the engine unit's memory.

The identifiers are in `app/app.json` (`config.dpf`), from the public SGBD reference of the G-series DDE 8.3 (B37 / B47 / B57).

## Install

From the MGU Store: add the source **`giuseppesalatino-boop/mgu-apps`** and install **DPF Monitoring** (see the [collection's README](../README.md)).

From a PC, with BMW's SDK in the collection's `vendor/idrive7-apps/oap-sdk/`: `npm run build:car` writes `dist/dpf_id7@<version>.mgu` (it contains BMW's SDK: for your own car only, never publish it), then install it with the kit's installer in `vendor/idrive7-apps/deploy`.

## Emulator

From this folder: `npm run emu`, then open http://localhost:8077. Without a DDE to answer, the app shows its demo values.

## Licence

MIT ([LICENSE](LICENSE)). Built on [idrive7-apps](https://github.com/cauliflowermossgrape/idrive7-apps) by cauliflowermossgrape (MIT), from its DPF Monitor. Not affiliated with or endorsed by BMW.
