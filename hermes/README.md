# NyxKeys Hermes

The standard Hermes: a 24-key numpad with a dedicated function row (F1–F4), optional 2U Plus, Enter and Zero keys, and a utility column on the right side.

| File | Description |
|---|---|
| [`hermes_main_v1.0.bin`](hermes_main_v1.0.bin) | Firmware v1.0 with VIA enabled |
| [`hermes_via.json`](hermes_via.json) | VIA definition (VID `0x1209` / PID `0x200B`) |

QMK source: [`Shiva1796/qmk_firmware` @ `hermes_main`](https://github.com/Shiva1796/qmk_firmware/tree/hermes_main/keyboards/nyxkeys/hermes) (keymap: [`default`](https://github.com/Shiva1796/qmk_firmware/tree/hermes_main/keyboards/nyxkeys/hermes/keymaps/default))

## Default keymap

| Layer | Access              | Contents |
|-------|---------------------|----------|
| 0     | Base                | F1–F4, numpad, Backspace, Enter, Tab. `Fn` is top-left of the numpad |
| 1     | Hold `Fn`           | F5–F8, F10–F12, arrows on 8/4/6/2, Home/End/PgUp/PgDn on 7/1/9/3 |
| 2     | Hold `Fn` then `.`  | `5` = Bootloader, `2` = Clear EEPROM |

## Using VIA

The Hermes is not in VIA's official keyboard list yet, so VIA will show *"could not find a v3 definition for Hermes"* until you load the definition file:

1. Download [`hermes_via.json`](hermes_via.json).
2. Open [usevia.app](https://usevia.app) in Chrome or Edge.
3. Open **Settings** and turn on **Show Design tab**.
4. In the **Design** tab, make sure **Use V2 definitions (deprecated)** is **off**.
5. Click **Load** and select `hermes_via.json`. It should show *NyxKeys Hermes*.
6. Switch to **Configure** and authorize the keyboard. If it doesn't appear, unplug and replug it.

VIA remembers the definition in your browser. Repeat these steps if you switch browsers or clear site data.

In the **Layouts** tab, set **Plus**, **Enter** and **Zero** to match your build: **2U** for a single large key, **Split** for two 1U keys.

## Flashing the firmware

1. Download [`hermes_main_v1.0.bin`](hermes_main_v1.0.bin) and install [QMK Toolbox](https://github.com/qmk/qmk_toolbox/releases).
2. Open QMK Toolbox and select the `.bin` file.
3. Put the Hermes into bootloader mode (see below). QMK Toolbox should show *"STM32 DFU device connected"*.
4. Click **Flash** and wait for it to finish.
5. Clear the EEPROM after flashing (`Fn` + `.` + `2`) so VIA picks up the default keymap.

## Bootloader

- **Bootmagic reset**: Hold F1 (top-left key) while plugging in the keyboard. This also clears the EEPROM.
- **Reset button**: Briefly press the button on the back of the PCB.
- **Key combo**: Hold `Fn`, then hold `.`, then press `5`.
