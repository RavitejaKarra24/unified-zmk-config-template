# Corne MX Keymap Guide

Adapted from the beekeeb Toucan keyboard config. 42-key split layout (6×3 + 3 thumb per side).

---

## How Behaviors Work

This keymap uses custom hold-tap behaviors extensively. Understanding them is key:

| Behavior | What it does |
|----------|-------------|
| `&kp X` | Simple keypress: tap sends X |
| `&my_mt HOLD TAP` | **Mod-Tap**: tap sends TAP, hold sends HOLD (300ms threshold) |
| `&my_lt LAYER TAP` | **Layer-Tap**: tap sends TAP, hold activates LAYER |
| `&lt LAYER TAP` | Same as `my_lt` but built-in ZMK behavior |
| `&hrm_l MOD TAP` | **Homerow Mod (left)**: tap sends TAP, hold sends MOD (300ms, tap-preferred) |
| `&hrm_r MOD TAP` | **Homerow Mod (right)**: same as above for right hand |
| `&mo LAYER` | **Momentary layer**: hold to activate LAYER |
| `&to LAYER` | **Toggle layer**: switch to LAYER permanently |
| `&trans` | **Transparent**: falls through to the layer below |
| `&none` | **Nothing**: key does nothing |

### Modifier Key Abbreviations

| Abbreviation | Key | macOS | Windows |
|-------------|-----|-------|---------|
| `LG()` / `LGUI` | Left GUI | Command (⌘) | Win key |
| `LA()` / `LALT` | Left Alt | Option (⌥) | Alt |
| `LC()` / `LCTRL` | Left Ctrl | Control (⌃) | Ctrl |
| `LS()` / `LSHFT` | Left Shift | Shift (⇧) | Shift |
| `RG/RA/RC/RS` | Right-side equivalents | Same | Same |

---

## Layer 0: BASE (macOS)

Default QWERTY with homerow mods. Optimized for macOS.

```
┌──────────┬────────┬──────────┬──────────┬──────────┬──────────┐          ┌──────────┬──────────┬────────┬──────────┬────────┬──────────┐
│ Tab/Ret  │   Q    │  W/Syst  │  E/⌥E    │ R/⌃⌘F19  │ T/⌘⌥F1   │          │    Y     │  U/⌘Z    │   I    │  O/Hyper │   P    │    \     │
├──────────┼────────┼──────────┼──────────┼──────────┼──────────┤          ├──────────┼──────────┼────────┼──────────┼────────┼──────────┤
│ Esc/Nav  │ A/Ctrl │ S/Shift  │  D/Alt   │  F/Cmd   │  G/⌃Z    │          │    H     │  J/Cmd   │ K/Alt  │ L/Shift  │ ;/Ctrl │    '     │
├──────────┼────────┼──────────┼──────────┼──────────┼──────────┤          ├──────────┼──────────┼────────┼──────────┼────────┼──────────┤
│  LShift  │ Z/⌘Tab │  X/⌘`   │  C/⌘C    │  V/⌘V    │ B/⌘⌥F8   │          │  N/⌥N    │ M/⌘⌥F9   │   ,    │  ./Hyper  │   /    │  RShift  │
└──────────┴────────┴──────────┴──────────┼──────────┼──────────┼────┐ ┌────┼──────────┼──────────┼────────┴──────────┴────────┴──────────┘
                                           │  (none)  │ Bksp/Sym │ Spc│ │Spc │ Ret/Subl │  (none)  │
                                           └──────────┴──────────┴────┘ └────┴──────────┴──────────┘
```

**Key features:**
- **Homerow mods** on the home row: A=Ctrl, S=Shift, D=Alt, F=Cmd (left); J=Cmd, K=Alt, L=Shift, ;=Ctrl (right)
- **Tab/Enter** on top-left: tap = Tab, hold = Enter
- **Esc/Nav** on left home: tap = Escape, hold = activate Nav layer
- **W/Syst**: tap = W, hold = activate System layer
- **Bksp/Sym**: tap = Backspace, hold = activate Symbols layer
- **Ret/Subl**: tap = Enter, hold = activate Sub-layer (gateway to all other layers)
- **Z/⌘Tab**: tap = Z, hold = Cmd+Tab (app switcher)
- **C/⌘C, V/⌘V**: tap = letter, hold = copy/paste
- **G/⌃Z**: tap = G, hold = Ctrl+Z (undo)
- **U/⌘Z**: tap = U, hold = Cmd+Z (undo on macOS)

---

## Layer 1: WNDS (Windows)

Same QWERTY layout but with Windows-optimized modifiers. Homerow mods swap Cmd↔Alt positions for Windows convention.

```
┌──────────┬────────┬──────────┬──────────┬──────────┬──────────┐          ┌──────────┬──────────┬────────┬──────────┬────────┬──────────┐
│ Tab/Ret  │   Q    │  W/Syst  │    E     │ R/⌃⌘F19  │ T/⌘⌥F1   │          │    Y     │  U/⌃Z    │   I    │    O     │   P    │    \     │
├──────────┼────────┼──────────┼──────────┼──────────┼──────────┤          ├──────────┼──────────┼────────┼──────────┼────────┼──────────┤
│ Esc/Nav  │ A/Ctrl │ S/Shift  │  D/Win   │  F/Alt   │    G     │          │    H     │  J/Alt   │ K/Win  │ L/Shift  │ ;/Ctrl │    '     │
├──────────┼────────┼──────────┼──────────┼──────────┼──────────┤          ├──────────┼──────────┼────────┼──────────┼────────┼──────────┤
│  LShift  │Z/HyperF6│X/HyperF7│  C/⌃C    │  V/⌃V    │    B     │          │    N     │    M     │   ,    │    .     │   /    │  RShift  │
└──────────┴────────┴──────────┴──────────┼──────────┼──────────┼────┐ ┌────┼──────────┼──────────┼────────┴──────────┴────────┴──────────┘
                                           │  (none)  │ Bksp/Sym │ Spc│ │Spc │ Ret/Subl │  (none)  │
                                           └──────────┴──────────┴────┘ └────┴──────────┴──────────┘
```

**Differences from BASE:**
- Homerow D = Win (not Alt), F = Alt (not Cmd) — matches Windows ergonomics
- Copy/Paste use Ctrl+C/V instead of Cmd+C/V
- Faster hold-tap timing (200ms vs 300ms) with retro-tap
- U sends Ctrl+Z (Windows undo) instead of Cmd+Z

---

## Layer 2: NAVI (Navigation)

Activated by holding **Esc** (left home row). Arrow keys, word selection, and window management.

```
┌──────────┬──────────┬──────────┬──────────┬──────────┬──────────┐          ┌──────────┬──────────┬──────────┬──────────┬──────────┬────┐
│ Hyp+Tab  │ Hyp+0    │ Hyp+W    │ Hyp+D    │  (trns)  │ Hyp+T    │          │ ⌥⇧+Left  │ ⌥⇧+Down  │ ⌥⇧+Up   │ ⌥⇧+Right │  (trns)  │    │
├──────────┼──────────┼──────────┼──────────┼──────────┼──────────┤          ├──────────┼──────────┼──────────┼──────────┼──────────┼────┤
│ (layer)  │ Hyp+=    │ Hyp+9    │  ⌘[      │  ⌘]      │ Hyp+G    │          │   Left   │   Down   │    Up    │  Right   │ Hyp+;    │    │
├──────────┼──────────┼──────────┼──────────┼──────────┼──────────┤          ├──────────┼──────────┼──────────┼──────────┼──────────┼────┤
│  (trns)  │  (trns)  │  (trns)  │  (trns)  │  (trns)  │ Hyp+B    │          │  (trns)  │  (trns)  │  (trns)  │  (trns)  │  (trns)  │    │
└──────────┴──────────┴──────────┴──────────┼──────────┼──────────┼────┐ ┌────┼──────────┼──────────┼──────────┴──────────┴──────────┴────┘
                                             │  (trns)  │  (none)  │none│ │trns│  (trns)  │  (trns)  │
                                             └──────────┴──────────┴────┘ └────┴──────────┴──────────┘
```

**Key bindings:**
- **Right hand home row**: Arrow keys (H=Left, J=Down, K=Up, L=Right) — Vim-style
- **Right hand top row**: Alt+Shift+Arrows — word/line selection
- **⌘[ / ⌘]**: Browser/Finder back/forward
- **Hyp+X** = Cmd+Ctrl+Alt+Shift+X (Hyper key combos for window managers)

---

## Layer 3: SYMB (Symbols)

Activated by holding **Backspace** (left thumb). All symbols and numbers.

```
┌────────┬────────┬────────┬────────┬────────┬────────┐          ┌────────┬────────┬────────┬────────┬────────┬────────┐
│   _    │   !    │   @    │   #    │   $    │   %    │          │   ^    │   &    │   *    │   (    │   )    │   -    │
├────────┼────────┼────────┼────────┼────────┼────────┤          ├────────┼────────┼────────┼────────┼────────┼────────┤
│   ~    │   1    │   2    │   3    │   4    │   5    │          │   6    │   7    │   8    │   9    │   0    │   `    │
├────────┼────────┼────────┼────────┼────────┼────────┤          ├────────┼────────┼────────┼────────┼────────┼────────┤
│   +    │   <    │   >    │   ?    │   [    │   ]    │          │   {    │   }    │   ,    │   .    │   /    │   =    │
└────────┴────────┴────────┴────────┼────────┼────────┼────┐ ┌────┼────────┼────────┼────────┴────────┴────────┴────────┘
                                     │ (trns) │ (held) │trns│ │trns│ (trns) │ (trns) │
                                     └────────┴────────┴────┘ └────┴────────┴────────┘
```

**Layout logic:**
- **Top row**: Shifted symbols (!@#$%^&*())
- **Middle row**: Numbers 1-0 with ~ and ` on the edges
- **Bottom row**: Brackets, comparison operators, math symbols

---

## Layer 4: SUBL (Sub-Layer Router)

Activated by holding **Enter** (right thumb). This is a gateway — hold a key here to reach deeper layers.

```
┌────────┬────────┬────────┬────────┬──────────┬──────────┐          ┌────────┬────────┬────────┬────────┬────────┬────────┐
│        │        │→ WORK  │        │→ RAYCAST │→ SESSION │          │        │        │        │→ OBS   │        │        │
├────────┼────────┼────────┼────────┼──────────┼──────────┤          ├────────┼────────┼────────┼────────┼────────┼────────┤
│        │        │→ LTRS  │        │          │          │          │        │        │        │        │        │        │
├────────┼────────┼────────┼────────┼──────────┼──────────┤          ├────────┼────────┼────────┼────────┼────────┼────────┤
│        │        │        │        │          │→ BLUE    │          │        │        │        │        │        │        │
└────────┴────────┴────────┴────────┼──────────┼──────────┼────┐ ┌────┼────────┼────────┼────────┴────────┴────────┴────────┘
                                     │          │→ APPS    │    │ │    │ (held) │        │
                                     └──────────┴──────────┴────┘ └────┴────────┴────────┘
```

**How to reach deeper layers** (hold Enter on right thumb, then hold):
- **W** → Work layer
- **R** → Raycast launcher
- **T** → Session management
- **S** → Letters layer
- **I** → OBS Studio control
- **B** → Bluetooth settings
- **Left thumb Bksp** → Apps layer

---

## Layer 5: APPS (Application Launcher)

Reached via **SUBL + Bksp**. 36 app launcher shortcuts using Shift+Ctrl+F-keys and Ctrl+Alt+F-keys. Map these to apps using macOS Shortcuts, Raycast, or Hammerspoon.

```
┌────────────┬────────────┬────────────┬────────────┬────────────┬────────────┐   ┌────────────┬────────────┬────────────┬────────────┬────────────┬────────────┐
│            │  ⇧⌃F1     │  ⇧⌃F2     │  ⇧⌃F3     │  ⇧⌃F4     │  ⇧⌃F5     │   │  ⇧⌃F6     │  ⇧⌃F7     │  ⇧⌃F8     │  ⇧⌃F9     │  ⇧⌃F10    │  ⇧⌃F11    │
├────────────┼────────────┼────────────┼────────────┼────────────┼────────────┤   ├────────────┼────────────┼────────────┼────────────┼────────────┼────────────┤
│            │  ⇧⌃F12    │  ⇧⌃F13    │  ⌃⌥F16    │  ⌃⌥F17    │  ⇧⌃F16    │   │  ⇧⌃F17    │  ⇧⌃F18    │  ⇧⌃F19    │  ⌃⌥F18    │  ⌃⌥F12    │  ⌃⌥F13    │
├────────────┼────────────┼────────────┼────────────┼────────────┼────────────┤   ├────────────┼────────────┼────────────┼────────────┼────────────┼────────────┤
│            │  ⌃⌥F1     │  ⌃⌥F2     │  ⌃⌥F3     │  ⌃⌥F4     │  ⌃⌥F5     │   │  ⌃⌥F6     │  ⌃⌥F7     │  ⌃⌥F8     │  ⌃⌥F9     │  ⌃⌥F10    │  ⌃⌥F11    │
└────────────┴────────────┴────────────┴────────────┴────────────┴────────────┘   └────────────┴────────────┴────────────┴────────────┴────────────┴────────────┘
```

---

## Layer 6: SESS (Session Management)

Reached via **SUBL + T**. Ctrl+Cmd+F-key combos for managing tmux sessions, terminal tabs, IDE workspaces, etc.

```
┌────────┬────────┬──────────┬──────────┬──────────┬────────┐          ┌──────────┬──────────┬──────────┬──────────┬──────────┬────────┐
│        │        │ ⇧⌥⌘F10  │  ⌃⌘F12  │  ⌃⌘F13  │        │          │  ⌃⌘F16  │  ⌃⌘F17  │  ⌃⌘F18  │  ⌃⌥F19  │  ⌃⌘F1   │        │
├────────┼────────┼──────────┼──────────┼──────────┼────────┤          ├──────────┼──────────┼──────────┼──────────┼──────────┼────────┤
│        │        │          │          │          │        │          │  ⌃⌘F2   │  ⌃⌘F3   │  ⌃⌘F4   │  ⌃⌘F5   │  ⌃⌘F6   │        │
├────────┼────────┼──────────┼──────────┼──────────┼────────┤          ├──────────┼──────────┼──────────┼──────────┼──────────┼────────┤
│        │        │          │          │          │        │          │  ⌃⌘F7   │  ⌃⌘F8   │  ⌃⌘F9   │  ⌃⌘F10  │  ⌃⌘F11  │        │
└────────┴────────┴──────────┴──────────┴──────────┴────────┘          └──────────┴──────────┴──────────┴──────────┴──────────┴────────┘
```

---

## Layer 7: SYST (System Controls)

Activated by holding **W** on the base layer. Media, volume, brightness, zoom, and window controls.

```
┌────────┬────────┬────────┬────────┬──────────┬────────┐          ┌────────┬────────┬────────┬────────┬────────┬────────┐
│        │ ⌘⌥F2  │        │ Vol Up │Zoom+/Yaba│ ⌘⌥F3  │          │  Prev  │ Bri Dn │ Bri Up │  Next  │ Play/P │        │
├────────┼────────┼────────┼────────┼──────────┼────────┤          ├────────┼────────┼────────┼────────┼────────┼────────┤
│  ⌘W    │  ⌘⌃Q  │        │ Vol Dn │  Zoom-   │ ⌘⌥F4  │          │ ⌘⇧[   │ ⌘⌥F6  │        │  ⌘⇧]   │        │        │
├────────┼────────┼────────┼────────┼──────────┼────────┤          ├────────┼────────┼────────┼────────┼────────┼────────┤
│        │        │        │        │          │        │          │ ⌘⌥F5  │ ⌘⌥F7  │        │        │        │        │
└────────┴────────┴────────┴────────┴──────────┴────────┘          └────────┴────────┴────────┴────────┴────────┴────────┘
```

**Key bindings:**
- **Vol Up / Vol Dn**: System volume
- **Bri Up / Bri Dn**: Screen brightness
- **Prev / Next / Play**: Media controls
- **⌘W**: Close window/tab
- **⌘⌃Q**: Lock screen (macOS)
- **Zoom+ / Zoom-**: ⌘= / ⌘- (browser/app zoom)
- **⌘⇧[ / ⌘⇧]**: Previous/next tab in most macOS apps
- **Zoom+** also activates **Yabai layer** on hold (Layer 8)

---

## Layer 8: YABA (Yabai Window Manager)

Reached by holding **Zoom+** in the System layer. Sends Shift+Alt+Ctrl+F-key combos for Yabai tiling window manager on macOS.

```
┌────────┬────────┬────────┬────────┬──────────┬────────┐          ┌──────────┬──────────┬──────────┬──────────┬────────┬────────┐
│        │        │        │        │ ⇧⌥⌃F10  │        │          │ ⇧⌥⌃F11  │ ⇧⌥⌃F12  │ ⇧⌥⌃F13  │ ⇧⌥⌃F16  │        │        │
├────────┼────────┼────────┼────────┼──────────┼────────┤          ├──────────┼──────────┼──────────┼──────────┼────────┼────────┤
│        │        │        │        │          │        │          │ ⇧⌥⌃F17  │ ⇧⌥⌃F18  │ ⇧⌥⌃F19  │ ⇧⌥⌘F1   │        │        │
├────────┼────────┼────────┼────────┼──────────┼────────┤          ├──────────┼──────────┼──────────┼──────────┼────────┼────────┤
│        │        │        │        │          │        │          │ ⇧⌥⌘F2   │ ⇧⌥⌘F3   │ ⇧⌥⌘F4   │ ⇧⌥⌘F5   │        │        │
└────────┴────────┴────────┴────────┴──────────┴────────┘          └──────────┴──────────┴──────────┴──────────┴────────┴────────┘
```

Map these in your Yabai config (e.g., focus window, move window, resize, swap, toggle float/fullscreen).

---

## Layer 9: RAYC (Raycast Launcher)

Reached via **SUBL + R**. Cmd+Alt+F-key and Shift+Cmd+F-key combos for Raycast extensions.

```
┌────────┬────────┬────────┬──────────┬────────┬────────┐          ┌──────────┬──────────┬──────────┬──────────┬──────────┬────────┐
│        │        │        │  ⌘⌥F10  │        │        │          │  ⌘⌥F18  │  ⌘⌥F19  │  ⇧⌘F1   │  ⇧⌘F2   │  ⇧⌘F3   │        │
├────────┼────────┼────────┼──────────┼────────┼────────┤          ├──────────┼──────────┼──────────┼──────────┼──────────┼────────┤
│        │        │        │          │        │        │          │  ⌘⌥F11  │  ⌘⌥F12  │  ⌘⌥F13  │  ⌘⌥F16  │  ⌘⌥F17  │        │
├────────┼────────┼────────┼──────────┼────────┼────────┤          ├──────────┼──────────┼──────────┼──────────┼──────────┼────────┤
│        │        │        │          │        │        │          │          │          │          │          │          │        │
└────────┴────────┴────────┴──────────┴────────┴────────┘          └──────────┴──────────┴──────────┴──────────┴──────────┴────────┘
```

---

## Layer 10: LTRS (Letters / Text Shortcuts)

Reached via **SUBL + S**. Shift+Cmd+F-key combos for text expansion, snippets, or special character shortcuts.

```
┌────────┬────────┬────────┬──────────┬────────┬────────┐          ┌──────────┬──────────┬──────────┬────────┬────────┬────────┐
│        │        │        │          │        │        │          │  ⇧⌘F5   │  ⇧⌘F6   │  ⇧⌘F7   │        │        │        │
├────────┼────────┼────────┼──────────┼────────┼────────┤          ├──────────┼──────────┼──────────┼────────┼────────┼────────┤
│        │        │        │  ⇧⌘F4   │        │        │          │  ⇧⌘F8   │  ⇧⌘F9   │  ⇧⌘F10  │        │        │        │
├────────┼────────┼────────┼──────────┼────────┼────────┤          ├──────────┼──────────┼──────────┼────────┼────────┼────────┤
│        │        │        │          │        │        │          │  ⇧⌘F11  │  ⇧⌘F12  │  ⇧⌘F13  │        │        │        │
└────────┴────────┴────────┴──────────┴────────┴────────┘          └──────────┴──────────┴──────────┴────────┴────────┴────────┘
```

---

## Layer 11: OBS (OBS Studio)

Reached via **SUBL + I**. Full OBS scene/source control using Shift+Alt+F-key combos.

```
┌────────┬──────────┬──────────┬──────────┬──────────┬──────────┐   ┌──────────┬──────────┬──────────┬──────────┬──────────┬────────┐
│        │  ⇧⌥F1   │  ⇧⌥F2   │  ⇧⌥F3   │  ⇧⌥F4   │  ⇧⌥F5   │   │  ⇧⌥F6   │  ⇧⌥F7   │  ⇧⌥F8   │          │→ OBSpos  │        │
├────────┼──────────┼──────────┼──────────┼──────────┼──────────┤   ├──────────┼──────────┼──────────┼──────────┼──────────┼────────┤
│        │  ⇧⌥F11  │  ⇧⌥F12  │  ⇧⌥F13  │  ⇧⌥F16  │  ⇧⌥F17  │   │  ⇧⌥F18  │  ⇧⌥F19  │  ⇧⌘F16  │  ⇧⌘F17  │  ⇧⌘F18  │        │
├────────┼──────────┼──────────┼──────────┼──────────┼──────────┤   ├──────────┼──────────┼──────────┼──────────┼──────────┼────────┤
│        │  ⇧⌘F19  │ ⇧⌥⌃F1   │ ⇧⌥⌃F2   │ ⇧⌥⌃F3   │ ⇧⌥⌃F4   │   │ ⇧⌥⌃F5   │ ⇧⌥⌃F6   │ ⇧⌥⌃F7   │ ⇧⌥⌃F8   │ ⇧⌥⌃F9   │        │
└────────┴──────────┴──────────┴──────────┴──────────┴──────────┘   └──────────┴──────────┴──────────┴──────────┴──────────┴────────┘
```

**Row mapping idea:** Top row = scenes, Middle row = sources, Bottom row = filters/transitions. Map in OBS → Settings → Hotkeys.

---

## Layer 12: BLUE (Bluetooth)

Reached via **SUBL + B**. Bluetooth profile management.

```
┌────────┬────────┬────────┬────────┬────────┬────────┐          ┌────────┬────────┬────────┬────────┬────────┬────────┐
│        │        │        │        │        │        │          │        │→ BASE  │→ WNDS  │        │        │        │
├────────┼────────┼────────┼────────┼────────┼────────┤          ├────────┼────────┼────────┼────────┼────────┼────────┤
│        │        │        │        │        │        │          │BT CLR  │ BT 0   │ BT 1   │ BT 2   │ BT 3   │ BT 4   │
├────────┼────────┼────────┼────────┼────────┼────────┤          ├────────┼────────┼────────┼────────┼────────┼────────┤
│        │        │        │        │        │        │          │        │        │        │        │        │        │
└────────┴────────┴────────┴────────┴────────┴────────┘          └────────┴────────┴────────┴────────┴────────┴────────┘
```

**Key bindings:**
- **BT 0–4**: Select Bluetooth profile (pair up to 5 devices)
- **BT CLR**: Clear current Bluetooth pairing
- **→ BASE**: Switch to macOS base layer permanently
- **→ WNDS**: Switch to Windows base layer permanently

---

## Layer 13: OBP (OBS Position)

Reached from OBS layer by holding the key at position (row 0, col 10). Fine-tune OBS source positioning.

```
┌────────┬──────────┬──────────┬──────────┬──────────┬────────┐          ┌──────┬──────┬──────┬──────┬──────┬──────┐
│        │          │          │          │          │        │          │      │      │      │      │      │      │
├────────┼──────────┼──────────┼──────────┼──────────┼────────┤          ├──────┼──────┼──────┼──────┼──────┼──────┤
│        │  ⇧⌥F9   │  ⇧⌥F10  │  ⇧⌥⌘F8  │  ⇧⌥⌘F9  │        │          │      │      │      │      │      │      │
├────────┼──────────┼──────────┼──────────┼──────────┼────────┤          ├──────┼──────┼──────┼──────┼──────┼──────┤
│        │          │          │          │          │        │          │      │      │      │      │      │      │
└────────┴──────────┴──────────┴──────────┴──────────┴────────┘          └──────┴──────┴──────┴──────┴──────┴──────┘
```

---

## Layer 14: WRK (Workspace)

Reached via **SUBL + W**. Shift+Alt+Cmd+F-key combos for workspace/virtual desktop management.

```
┌────────┬────────┬────────┬────────┬──────────┬────────┐          ┌────────┬──────────┬──────────┬──────────┬──────────┬────────┐
│        │        │        │        │          │        │          │        │          │          │ ⇧⌥⌘F12  │          │        │
├────────┼────────┼────────┼────────┼──────────┼────────┤          ├────────┼──────────┼──────────┼──────────┼──────────┼────────┤
│        │        │        │        │ ⇧⌥⌘F18  │        │          │        │ ⇧⌥⌘F16  │ ⇧⌥⌘F11  │          │ ⇧⌥⌘F17  │        │
├────────┼────────┼────────┼────────┼──────────┼────────┤          ├────────┼──────────┼──────────┼──────────┼──────────┼────────┤
│        │        │        │        │          │        │          │        │ ⇧⌥⌘F13  │          │          │          │        │
└────────┴────────┴────────┴────────┴──────────┴────────┘          └────────┴──────────┴──────────┴──────────┴──────────┴────────┘
```

---

## Layer Access Cheat Sheet

```
BASE ──hold Esc────→ NAV (arrows, vim-style navigation)
     ──hold W──────→ SYST (volume, brightness, media)
     │                └──hold Zoom+──→ YABAI (window tiling)
     ──hold Bksp───→ SYMB (numbers, symbols, brackets)
     ──hold Enter──→ SUBL (sub-layer gateway)
                       ├──hold W──→ WORK (workspace mgmt)
                       ├──hold S──→ LTRS (text shortcuts)
                       ├──hold R──→ RAYC (Raycast launcher)
                       ├──hold T──→ SESS (session mgmt)
                       ├──hold I──→ OBS (OBS Studio)
                       │             └──hold P area──→ OBSpos
                       ├──hold B──→ BLUE (Bluetooth profiles)
                       └──hold Bksp──→ APPS (app launcher)
```

---

## OLED Display

Your OLEDs show:

**Left half (central):**
- Bongo Cat animation (types faster as your WPM increases)
- WPM speedometer gauge + number
- Active modifier indicators (⌘ ⌥ ⇧ ⌃ in macOS symbols)
- Current layer name
- BLE profile / USB connection status
- Battery percentage
- CapsLock indicator

**Right half (peripheral):**
- Animated cat
- Smart battery indicator
- Sleep art when keyboard goes idle

---

## Customization Tips

1. **Remap the F-key combos**: Layers 5–14 use F-key combos as "virtual hotkeys." Map them to actual actions in your OS using Raycast, Hammerspoon, Karabiner, BetterTouchTool (macOS) or AutoHotkey (Windows).

2. **Switch between macOS/Windows**: Use the Bluetooth layer to toggle between BASE (Layer 0, macOS) and WNDS (Layer 1, Windows) with `→ BASE` and `→ WNDS`.

3. **Tune homerow mods**: If you get accidental mod triggers, increase `tapping-term-ms` in the keymap behaviors. If mods feel sluggish, decrease it.

4. **Edit the keymap**: Modify `config/corne.keymap`, push to GitHub, download the built firmware from Actions, and flash.
