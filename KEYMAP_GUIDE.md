# Corne MX Keymap Guide

5-layer split layout (42 keys) for macOS dev workflow with Aerospace, nvim, Vimium, and Alfred.

---

## Layer Access

```
BASE ──hold Esc────→ NAV   (arrows, screenshots, clipboard)
     ──hold Bksp───→ SYMB  (numbers, symbols, brackets)
     ──hold Enter──→ MEDIA (Aerospace, tabs, volume, brightness, mic, DND)
                       └──hold B──→ ADJUST (Bluetooth profiles)
```

**Combos (simultaneous press):**

| Keys | Action |
|------|--------|
| J + K | Escape (works everywhere, not just nvim) |
| LShift + RShift | Caps Word (auto-caps for SNAKE_CASE, turns off at space) |

---

## How Behaviors Work

| Behavior | What it does |
|----------|-------------|
| `&kp X` | Simple keypress: tap sends X |
| `&my_mt HOLD TAP` | **Mod-Tap**: tap sends TAP, hold sends HOLD (300ms) |
| `&hrm_l MOD TAP` | **Homerow Mod (left)**: tap sends TAP, hold sends MOD (300ms, tap-preferred) |
| `&hrm_r MOD TAP` | **Homerow Mod (right)**: same as above for right hand |
| `&lt LAYER TAP` | **Layer-Tap**: tap sends TAP, hold activates LAYER |
| `&mo LAYER` | **Momentary layer**: hold to activate LAYER |
| `&trans` | **Transparent**: falls through to the layer below |
| `&none` | **Nothing**: key does nothing |
| `&caps_word` | **Caps Word**: auto-capitalize until space/punctuation |

### Modifier Abbreviations

| Abbreviation | Key | macOS |
|-------------|-----|-------|
| `LG()` / `LGUI` | Left GUI | Command (⌘) |
| `LA()` / `LALT` | Left Alt | Option (⌥) |
| `LC()` / `LCTRL` | Left Ctrl | Control (⌃) |
| `LS()` / `LSHFT` | Left Shift | Shift (⇧) |

---

## Layer 0: BASE

QWERTY with homerow mods. Optimized for macOS.

```
┌──────────┬────────┬────────┬────────┬────────┬────────┐          ┌────────┬────────┬────────┬────────┬────────┬────────┐
│   Tab    │   Q    │   W    │   E    │   R    │   T    │          │   Y    │   U    │   I    │   O    │   P    │   \    │
├──────────┼────────┼────────┼────────┼────────┼────────┤          ├────────┼────────┼────────┼────────┼────────┼────────┤
│ Esc/NAV  │ A/Ctrl │S/Shift │ D/Opt  │ F/Cmd  │   G    │          │   H    │ J/Cmd  │ K/Opt  │L/Shift │ ;/Ctrl │   '    │
├──────────┼────────┼────────┼────────┼────────┼────────┤          ├────────┼────────┼────────┼────────┼────────┼────────┤
│  LShift  │ Z/⌘Tab │ X/⌘X   │ C/⌘C   │ V/⌘V   │   B    │          │   N    │   M    │   ,    │   .    │   /    │ RShift │
└──────────┴────────┴────────┴────────┼────────┼────────┼────┐┌────┼────────┼────────┼────────┴────────┴────────┴────────┘
                                       │ (none) │Bk/SYMB │ Spc││Spc │Ent/MED │ (none) │
                                       └────────┴────────┴────┘└────┴────────┴────────┘
```

**Homerow mods** (hold the key instead of tapping):

- Left hand: A = Ctrl, S = Shift, D = Option, F = Cmd
- Right hand: J = Cmd, K = Option, L = Shift, ; = Ctrl
- These give you every modifier combo: hold F + tap C = ⌘C, hold D + tap 1 (on SYMB) = ⌥1, etc.

**Useful hold-taps on bottom row:**

- Z hold = ⌘Tab (app switcher)
- X hold = ⌘X (cut)
- C hold = ⌘C (copy)
- V hold = ⌘V (paste)

**Thumb keys:**

- Left: Backspace (tap) / SYMB layer (hold)
- Right: Enter (tap) / MEDIA layer (hold)

---

## Layer 1: NAV (hold Esc)

Vim-style navigation. Left homerow mods are transparent so Shift+Arrow text selection works.

```
┌────────┬────────┬────────┬────────┬────────┬────────┐          ┌────────┬────────┬────────┬────────┬────────┬────────┐
│  ⌘⇧3   │  ⌘⇧4   │  ⌘⇧5   │        │        │  ⌘`    │          │  ⌥←    │  PgDn  │  PgUp  │  ⌥→    │  Del   │        │
├────────┼────────┼────────┼────────┼────────┼────────┤          ├────────┼────────┼────────┼────────┼────────┼────────┤
│ (held) │ (Ctrl) │(Shift) │ (Opt)  │ (Cmd)  │        │          │   ←    │   ↓    │   ↑    │   →    │        │        │
├────────┼────────┼────────┼────────┼────────┼────────┤          ├────────┼────────┼────────┼────────┼────────┼────────┤
│(Shift) │  ⌘Z    │  ⌘X    │  ⌘C    │  ⌘V    │        │          │  Home  │  End   │  ⌘[    │  ⌘]    │        │        │
└────────┴────────┴────────┴────────┼────────┼────────┼────┐┌────┼────────┼────────┼────────┴────────┴────────┴────────┘
                                     │ (trns) │  Del   │trns││trns│ (trns) │ (trns) │
                                     └────────┴────────┴────┘└────┴────────┴────────┘
```

**Right hand — navigation:**

| Key | Action |
|-----|--------|
| H / J / K / L | Arrow keys (vim-style) |
| ⌥← / ⌥→ | Jump word left/right |
| PgDn / PgUp | Page down/up |
| Home / End | Line start/end |
| Del | Forward delete |
| ⌘[ / ⌘] | Browser/Finder back/forward |

**Left hand — actions while navigating:**

| Key | Action |
|-----|--------|
| ⌘⇧3 | Screenshot (full screen) |
| ⌘⇧4 | Screenshot (region select) |
| ⌘⇧5 | Screenshot toolbar (record) |
| ⌘` | Cycle windows of same app |
| Home row | Transparent: homerow mods fall through for Shift+Arrow selections |
| ⌘Z / ⌘X / ⌘C / ⌘V | Undo / Cut / Copy / Paste |
| Del (left thumb) | Forward delete |

**Tip:** Hold Esc (NAV) + hold S (Shift via homerow) + tap L (→) = Shift+Right = select one character.

---

## Layer 2: SYMB (hold Bksp)

Numbers and symbols. Unchanged from original — already well-designed for coding.

```
┌────────┬────────┬────────┬────────┬────────┬────────┐          ┌────────┬────────┬────────┬────────┬────────┬────────┐
│   _    │   !    │   @    │   #    │   $    │   %    │          │   ^    │   &    │   *    │   (    │   )    │   -    │
├────────┼────────┼────────┼────────┼────────┼────────┤          ├────────┼────────┼────────┼────────┼────────┼────────┤
│   ~    │   1    │   2    │   3    │   4    │   5    │          │   6    │   7    │   8    │   9    │   0    │   `    │
├────────┼────────┼────────┼────────┼────────┼────────┤          ├────────┼────────┼────────┼────────┼────────┼────────┤
│   +    │   <    │   >    │   ?    │   [    │   ]    │          │   {    │   }    │   ,    │   .    │   /    │   =    │
└────────┴────────┴────────┴────────┼────────┼────────┼────┐┌────┼────────┼────────┼────────┴────────┴────────┴────────┘
                                     │ (trns) │ (held) │trns││trns│ (trns) │ (trns) │
                                     └────────┴────────┴────┘└────┴────────┴────────┘
```

**Layout logic:**

- Top row: shifted symbols (`!@#$%^&*()`)
- Home row: numbers `1-0` with `~` and `` ` `` on edges
- Bottom row: brackets, comparison operators, math (`<>?[]{}`)

---

## Layer 3: MEDIA (hold Enter)

Left side = workspace and tab management. Right side = media and system controls.

```
┌────────┬────────┬────────┬────────┬────────┬────────┐          ┌────────┬────────┬────────┬────────┬────────┬────────┐
│  ⌥1    │  ⌥2    │  ⌥3    │  ⌥4    │  ⌥5    │  ⌥6    │          │        │ Bri Dn │ Bri Up │        │        │        │
├────────┼────────┼────────┼────────┼────────┼────────┤          ├────────┼────────┼────────┼────────┼────────┼────────┤
│  ⌘1    │  ⌘2    │  ⌘3    │  ⌘4    │  ⌘5    │  ⌘6    │          │  Prev  │ Vol Dn │ Vol Up │  Next  │ Play/P │  Mute  │
├────────┼────────┼────────┼────────┼────────┼────────┤          ├────────┼────────┼────────┼────────┼────────┼────────┤
│  ⌃⇧1   │  ⌃⇧2   │  ⌃⇧3   │  ⌃⇧4   │  ⌃⇧5   │→ ADJ   │          │  Mic*  │  DND*  │  Lock  │  ⌘⇧[   │  ⌘⇧]   │        │
└────────┴────────┴────────┴────────┼────────┼────────┼────┐┌────┼────────┼────────┼────────┴────────┴────────┴────────┘
                                     │ (trns) │ (trns) │trns││trns│ (held) │ (trns) │
                                     └────────┴────────┴────┘└────┴────────┴────────┘
```

**Left hand — workspace/tab management (rows aligned by number):**

| Row | Keys | Action |
|-----|------|--------|
| Top | ⌥1 – ⌥6 | Aerospace: switch to workspace 1–6 |
| Home | ⌘1 – ⌘6 | Jump to browser/terminal tab 1–6 |
| Bottom | ⌃⇧1 – ⌃⇧5 | Aerospace: assign app to workspace 1–5 |
| Bottom-right | → ADJ | Hold to access Bluetooth (ADJUST layer) |

**Right hand — system controls:**

| Key | Action |
|-----|--------|
| Bri Dn / Bri Up | Screen brightness |
| Prev / Next | Previous / next track |
| Vol Dn / Vol Up | Volume down / up |
| Play/P | Play / pause |
| Mute | Audio mute |
| Mic* | Microphone toggle (F13 — see setup below) |
| DND* | Do Not Disturb toggle (F14 — see setup below) |
| Lock | Lock screen (⌘⌃Q) |
| ⌘⇧[ / ⌘⇧] | Previous / next tab (works in most macOS apps) |

---

## Layer 4: ADJ (hold B on MEDIA)

Bluetooth profile management. Accessed via: hold Enter + hold B.

```
┌────────┬────────┬────────┬────────┬────────┬────────┐          ┌────────┬────────┬────────┬────────┬────────┬────────┐
│        │        │        │        │        │        │          │        │        │        │        │        │        │
├────────┼────────┼────────┼────────┼────────┼────────┤          ├────────┼────────┼────────┼────────┼────────┼────────┤
│        │        │        │        │        │        │          │ BT CLR │  BT 0  │  BT 1  │  BT 2  │  BT 3  │  BT 4  │
├────────┼────────┼────────┼────────┼────────┼────────┤          ├────────┼────────┼────────┼────────┼────────┼────────┤
│        │        │        │        │        │        │          │        │        │        │        │        │        │
└────────┴────────┴────────┴────────┼────────┼────────┼────┐┌────┼────────┼────────┼────────┴────────┴────────┴────────┘
                                     │        │        │    ││    │        │        │
                                     └────────┴────────┴────┘└────┴────────┴────────┘
```

- **BT 0–4**: Select Bluetooth profile (pair up to 5 devices)
- **BT CLR**: Clear current Bluetooth pairing

---

## macOS Setup (one-time)

### Microphone Toggle (F13)

The Mic key sends F13. Map it to toggle microphone:

1. Open **System Settings → Keyboard → Keyboard Shortcuts → Microphone**
2. Enable the shortcut and set it to **F13**

### Do Not Disturb Toggle (F14)

The DND key sends F14. Map it via Apple Shortcuts:

1. Open the **Shortcuts** app
2. Create a new shortcut: action = "Set Focus" → "Do Not Disturb" → "Toggle"
3. Assign keyboard shortcut **F14** to this shortcut

### Aerospace

Ensure your `~/.aerospace.toml` uses these bindings (they should already match defaults):

```toml
# Workspace switching
alt-1 = 'workspace 1'
alt-2 = 'workspace 2'
alt-3 = 'workspace 3'
alt-4 = 'workspace 4'
alt-5 = 'workspace 5'
alt-6 = 'workspace 6'

# Assign app to workspace
ctrl-shift-1 = 'move-node-to-workspace 1'
ctrl-shift-2 = 'move-node-to-workspace 2'
ctrl-shift-3 = 'move-node-to-workspace 3'
ctrl-shift-4 = 'move-node-to-workspace 4'
ctrl-shift-5 = 'move-node-to-workspace 5'
```

---

## Tips for Vim / Vimium Users

- **Escape**: Tap Esc (left home position) or use the J+K combo from any app
- **Ctrl+[**: Alternative Esc — hold A (Ctrl via homerow) + tap [ (on SYMB layer, but easier to just use J+K)
- **Ctrl+C/D/U**: Hold A (Ctrl) + tap the letter — works naturally with homerow mods
- **Cmd+L**: Hold F (Cmd) + tap L = focus browser address bar (Vimium `o` also works)
- **Shift+Arrow selection**: Hold Esc (NAV) + hold S (Shift via homerow) + tap HJKL arrows

---

## Customization

1. **Tune homerow mods**: If you get accidental mod triggers during fast typing, increase `tapping-term-ms` (currently 300ms) or add `require-prior-idle-ms = <150>` to the `hrm_l` / `hrm_r` behaviors. If mods feel sluggish, decrease.

2. **Edit the keymap**: Modify `config/corne.keymap`, push to GitHub, download firmware from Actions, flash.

3. **Add more Aerospace workspaces**: The MEDIA layer supports 6 switch slots (⌥1–⌥6) and 5 assign slots (⌃⇧1–⌃⇧5). To add more, replace `&none` keys on the MEDIA layer right side.

---

## OLED Display

**Left half (central):**
- Bongo Cat animation (types faster as WPM increases)
- WPM speedometer + number
- Active modifier indicators (⌘ ⌥ ⇧ ⌃)
- Current layer name
- Battery percentage

**Right half (peripheral):**
- Animated cat
- Smart battery indicator
- Sleep art when idle
