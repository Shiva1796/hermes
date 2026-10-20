# NyxKeys Hermes

![NyxKeys Hermes](https://imagedelivery.net/5Lj-4KVs36OWCtiVSZ4L1Q/ea8b3594-f606-4271-d9d8-52596f303f00/public)

Firmware, VIA definitions and documentation for the NyxKeys Hermes 24-key numpad.

The Hermes comes in two versions. Pick the folder that matches your board:

| Version | Utility column | Folder | Firmware | VIA file |
|---|---|---|---|---|
| **Hermes** | Right | [`hermes/`](hermes/) | `hermes_main_v1.0.bin` | `hermes_via.json` |
| **Hermes SP** (southpaw) | Left | [`hermes_sp/`](hermes_sp/) | `hermes_sp_main_v1.0.bin` | `hermes_sp_via.json` |

Each folder has its own README with the keymap, VIA setup and flashing instructions.

## Switch plates

Plate files are in [`plates/`](plates/):

| Plate | Solder PCB (Hermes only) | Hot-swap PCB (Hermes and Hermes SP) |
|---|---|---|
| `Hermes Switch Plate HS 1.0.DXF` | ✗ | ✓ |
| `Hermes Switch Plate Solder.DXF` | ✓ | ✓ |

> **Note:** Hermes and Hermes SP (southpaw) use the **same plate files**. The solder plate fits every Hermes PCB; the hot-swap plate does not fit the solder PCB. The Hermes SP is hot-swap only.

## QMK source

The firmware is built from the NyxKeys fork of QMK:

- Hermes: [`Shiva1796/qmk_firmware` @ `hermes_main`](https://github.com/Shiva1796/qmk_firmware/tree/hermes_main/keyboards/nyxkeys/hermes)
- Hermes SP: [`Shiva1796/qmk_firmware` @ `hermes_sp_main`](https://github.com/Shiva1796/qmk_firmware/tree/hermes_sp_main/keyboards/nyxkeys/hermes)

## Links

- Store: [nyxkeys.com](https://nyxkeys.com)
- VIA: [usevia.app](https://usevia.app)
- QMK Toolbox (for flashing): [github.com/qmk/qmk_toolbox](https://github.com/qmk/qmk_toolbox/releases)
