# NyxKeys Hermes SP (Southpaw)

The southpaw Hermes: a mirrored 24-key numpad with a dedicated function row (F4–F1), optional 2U Plus, Enter and Zero keys, and a utility column on the left side.

| File | Description |
|---|---|
| [`hermes_sp_main_v1.0.bin`](hermes_sp_main_v1.0.bin) | Firmware v1.0 with VIA enabled |
| [`hermes_sp_via.json`](hermes_sp_via.json) | VIA definition (VID `0x1210` / PID `0x201B`) |

QMK source: [`Shiva1796/qmk_firmware` @ `hermes_sp_main`](https://github.com/Shiva1796/qmk_firmware/tree/hermes_sp_main/keyboards/nyxkeys/hermes) (keymap: [`default_sp`](https://github.com/Shiva1796/qmk_firmware/tree/hermes_sp_main/keyboards/nyxkeys/hermes/keymaps/default_sp))

## Default keymap

| Layer | Access              | Contents |
|-------|---------------------|----------|
| 0     | Base                | F4–F1, mirrored numpad, Backspace, Enter, Tab. `Fn` is top-right of the numpad |
| 1     | Hold `Fn`           | F5–F8, F10–F12, arrows on 8/6/4/2, PgUp/PgDn/Home/End on 9/3/7/1 |
| 2     | Hold `Fn` then `.`  | `5` = Bootloader, `2` = Clear EEPROM |

## Using VIA

The Hermes SP is not in VIA's official keyboard list yet, so VIA will show *"could not find a v3 definition for Hermes SP"* until you load the definition file:

1. Download [`hermes_sp_via.json`](hermes_sp_via.json).
2. Open [usevia.app](https://usevia.app) in Chrome or Edge.
3. Open **Settings** and turn on **Show Design tab**.
4. In the **Design** tab, make sure **Use V2 definitions (deprecated)** is **off**.
5. Click **Load** and select `hermes_sp_via.json`. It should show *NyxKeys Hermes SP*.
6. Switch to **Configure** and authorize the keyboard. If it doesn't appear, unplug and replug it.

VIA remembers the definition in your browser. Repeat these steps if you switch browsers or clear site data.

In the **Layouts** tab, set **Plus**, **Enter** and **Zero** to match your build: **2U** for a single large key, **Split** for two 1U keys.

## Flashing the firmware

1. Download [`hermes_sp_main_v1.0.bin`](hermes_sp_main_v1.0.bin) and install [QMK Toolbox](https://github.com/qmk/qmk_toolbox/releases).
2. Open QMK Toolbox and select the `.bin` file.
3. Put the Hermes SP into bootloader mode (see below). QMK Toolbox should show *"STM32 DFU device connected"*.
4. Click **Flash** and wait for it to finish.
5. Clear the EEPROM after flashing (`Fn` + `.` + `2`) so VIA picks up the default keymap.

## Bootloader

- **Bootmagic reset**: Hold F1 (top-right key) while plugging in the keyboard. This also clears the EEPROM.
- **Reset button**: Briefly press the button on the back of the PCB.
- **Key combo**: Hold `Fn`, then hold `.`, then press `5`.
