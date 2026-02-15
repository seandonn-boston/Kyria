# Kyria Rev3 Keymap Reference

Splitkb Kyria Rev3 running ZMK on nice!nano v2.
Five layers, OS-aware modifiers, rotary encoders, RGB, OLED, and mouse buttons.

---

## Smart Features

### Ctrl/Esc (Hold-Tap)
Top-left key does double duty. **Tap** for Escape, **hold** for Left Control.
No more reaching for a dedicated Ctrl key with your pinky.

### Sticky Shift (One-Shot)
Left Shift is a sticky/one-shot key. Two ways to use it:
- **Hold** it like normal shift to capitalize while held
- **Tap and release** it, then the next key you press will be shifted automatically

Perfect for single capital letters without holding anything down.

### Caps Word
Replaces Caps Lock (right inner column). Activates smart caps mode:
- All letters are automatically shifted
- Underscore, hyphen, backspace, and numbers keep it active
- Deactivates on space, enter, or any other key

Ideal for typing `SCREAMING_SNAKE_CASE` constants.

### Tri-Layer (Conditional)
Hold **HYPER + SUPER** at the same time to activate the **ADJUST** layer.
No dedicated ADJUST key needed -- the right outermost thumb is now Key Repeat.

### Key Repeat
Right outermost thumb key. Repeats whatever key you last pressed.
Useful for arrow key navigation, deleting multiple characters, or any repetitive input.

---

## OS Modifier Mode

Three keys change behavior depending on your OS. Set in `config/kyria_rev3.keymap` lines 25-27.

| Key     | Mac (current) | PC            |
|---------|---------------|---------------|
| OS_MOD1 | `LGUI` (Cmd)  | `LCTRL`       |
| OS_MOD2 | `RCTRL`       | `K_APP` (Menu)|
| OS_MOD3 | `K_APP` (Menu)| `RGUI` (Win)  |

---

## Layer 0: QWERTY (Default)

```
,-------------------------------------------.                              ,-------------------------------------------.
|Ctrl/Esc|   Q  |   W  |   E  |   R  |   T  |                              |   Y  |   U  |   I  |   O  |   P  |  Bksp  |
|--------+------+------+------+------+------|                              |------+------+------+------+------+--------|
|  Tab   |   A  |   S  |   D  |   F  |   G  |                              |   H  |   J  |   K  |   L  |  ; : | Enter  |
|--------+------+------+------+------+------+-------------.  ,-------------+------+------+------+------+------+--------|
| Sticky |   Z  |   X  |   C  |   V  |   B  |RClick|[SUP] |  |CapWrd|LClick|   N  |   M  |  , < |  . > |  / ? | [HYP]  |
| LShift |      |      |      |      |      |      |      |  |      |      |      |      |      |      |      |        |
`----------------------+------+------+------+------+------|  |------+------+------+------+------+----------------------'
                       |[FUNC]| LAlt |OS_MOD| Space|  [ { |  |  ] } |  ' " |OS_MOD|OS_MOD|KeyRpt|
                       |      |      |  1   |      |      |  |      |      |  2   |  3   |      |
                       `----------------------------------'  `----------------------------------'

Left Encoder: Right / Left arrows          Right Encoder: Down / Up arrows
```

**Key details:**
- `Ctrl/Esc` = hold for Ctrl, tap for Esc
- `Sticky LShift` = tap for one-shot shift, hold for regular shift
- `CapWrd` = Caps Word (smart caps, auto-deactivates)
- `KeyRpt` = repeats last key pressed
- `[SUP]`, `[HYP]`, `[FUNC]` = hold to activate that layer
- `[HYP] + [SUP]` held together = activates ADJUST layer (tri-layer)
- `RClick` / `LClick` = mouse right/left click
- `OS_MOD 1/2/3` = OS-dependent keys (see table above)

---

## Layer 1: HYPER (Numbers & Symbols)

Hold `[HYP]` (right pinky, bottom row) to activate.

```
,-------------------------------------------.                              ,-------------------------------------------.
|   `    |   1  |   2  |   3  |   4  |   5  |                              |   6  |   7  |   8  |   9  |   0  |   =    |
|--------+------+------+------+------+------|                              |------+------+------+------+------+--------|
|   ~    |   !  |   @  |   #  |   $  |   %  |                              |   ^  |   &  |   *  |   (  |   )  |   +    |
|--------+------+------+------+------+------+-------------.  ,-------------+------+------+------+------+------+--------|
|   |    |   \  |   :  |   ;  |   -  |   [  |   {  |      |  |      |   }  |   ]  |   _  |   ,  |   .  |   /  |   ?    |
`----------------------+------+------+------+------+------|  |------+------+------+------+------+----------------------'
                       |      |      |      |      |      |  |      |   `  |      |      |      |
                       `----------------------------------'  `----------------------------------'

Left Encoder: Right / Left arrows          Right Encoder: Down / Up arrows
```

**Design notes:**
- Top row = unshifted number row
- Middle row = shifted number row (symbols)
- Bottom row = punctuation pairs mirrored across halves
- Grave accent (`` ` ``) available on right thumb for quick access

---

## Layer 2: SUPER (Navigation & Media)

Hold `[SUP]` (left inner column, bottom row) to activate.

```
,-------------------------------------------.                              ,-------------------------------------------.
|        |      |      |      |      |      |                              | PgUp | Home |  Up  | End  | Vol+ | Delete |
|--------+------+------+------+------+------|                              |------+------+------+------+------+--------|
|        |  GUI |  Alt | Ctrl | Shift|      |                              | PgDn | Left | Down | Right| Vol- | Insert |
|--------+------+------+------+------+------+-------------.  ,-------------+------+------+------+------+------+--------|
|        |      |      |      |      |      |      |ScLck |  |ScLck |      |Pause | Prev | Play | Next | Mute | PrtSc  |
`----------------------+------+------+------+------+------|  |------+------+------+------+------+----------------------'
                       |      |      |      |      |      |  |NumLck|      |      |      |      |
                       `----------------------------------'  `----------------------------------'

Left Encoder: Right / Left arrows          Right Encoder: Down / Up arrows
```

**Key details:**
- Left home row has GACS modifiers for chording with nav keys
- Arrow cluster in inverted-T on the right
- Volume and media transport controls on the right edge
- `ScLck` = Scroll Lock on both inner keys
- `NumLck` = Num Lock on right thumb

---

## Layer 3: FUNCTION (F-Keys)

Hold `[FUNC]` (left thumb, outermost) to activate.

```
,-------------------------------------------.                              ,-------------------------------------------.
|        |  F9  | F10  | F11  | F12  |      |                              |      |      |      |      |      |        |
|--------+------+------+------+------+------|                              |------+------+------+------+------+--------|
|        |  F5  |  F6  |  F7  |  F8  |      |                              |      |RShift| RCtrl| LAlt | RGUI |        |
|--------+------+------+------+------+------+-------------.  ,-------------+------+------+------+------+------+--------|
|        |  F1  |  F2  |  F3  |  F4  |      |      |      |  |      |      |      |      |      |      |      |        |
`----------------------+------+------+------+------+------|  |------+------+------+------+------+----------------------'
                       |      |      |      |      |      |  |      |      |      |      |      |
                       `----------------------------------'  `----------------------------------'

Left Encoder: Right / Left arrows          Right Encoder: Down / Up arrows
```

**Key details:**
- F-keys arranged in a 4x3 numpad pattern on the left
- Right home row has mirrored GACS modifiers for chording (e.g. Alt+F4)
- The Alt key here is `LALT` (not `RALT`/AltGr) so shortcuts like Alt+F4 work correctly

---

## Layer 4: ADJUST (Bluetooth, RGB)

Activated by holding **HYPER + SUPER** simultaneously (tri-layer).

```
,-------------------------------------------.                              ,-------------------------------------------.
|        |BT CLR|      |      |      |BT PRV|                              |BT NXT|      |      |      |      |        |
|--------+------+------+------+------+------|                              |------+------+------+------+------+--------|
|        | BT 0 | BT 1 | BT 2 | BT 3 | BT 4 |                              |RGB On| Sat+ | Hue+ | Bri+ | Eff+ |        |
|--------+------+------+------+------+------+-------------.  ,-------------+------+------+------+------+------+--------|
|        |      |      |      |      |      |      |      |  |      |      |      | Sat- | Hue- | Bri- | Eff- |        |
`----------------------+------+------+------+------+------|  |------+------+------+------+------+----------------------'
                       |      |      |      |      |      |  |      |      |      |      |      |
                       `----------------------------------'  `----------------------------------'

Left Encoder: Vol+ / Vol-                  Right Encoder: PgUp / PgDn
```

**Bluetooth controls (left side):**
| Key      | Action                              |
|----------|-------------------------------------|
| BT CLR   | Clear current Bluetooth bond        |
| BT 0-4   | Select Bluetooth profile 0 through 4|
| BT PRV   | Switch to previous BT profile       |
| BT NXT   | Switch to next BT profile           |

**RGB controls (right side):**
| Key    | Action                         |
|--------|--------------------------------|
| RGB On | Toggle RGB underglow on/off    |
| Sat+/- | Increase/decrease saturation   |
| Hue+/- | Cycle hue up/down              |
| Bri+/- | Increase/decrease brightness   |
| Eff+/- | Cycle through RGB effects      |

---

## Rotary Encoders

| Layer               | Left Encoder (CW/CCW) | Right Encoder (CW/CCW) |
|---------------------|----------------------|------------------------|
| QWERTY / HYP / SUP / FUNC | Right / Left         | Down / Up              |
| ADJUST              | Vol+ / Vol-          | PgUp / PgDn            |

---

## Hardware Configuration

Enabled in `config/kyria_rev3.conf`:

| Feature         | Config                              |
|-----------------|-------------------------------------|
| Rotary encoders | `CONFIG_EC11=y`                     |
| OLED display    | `CONFIG_ZMK_DISPLAY=y`              |
| RGB underglow   | `CONFIG_ZMK_RGB_UNDERGLOW=y`        |
| Mouse buttons   | `CONFIG_ZMK_POINTING=y`             |

LED chain length set to 31 (per-key + underglow) in the keymap file.
