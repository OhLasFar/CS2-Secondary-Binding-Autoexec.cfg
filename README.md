
# CS2 Secondary Binding Autoexec

This repo ships a ready-to-play `autoexec.cfg` that lets you toggle a secondary layer of binds (perfect for utility) without losing your default layout. Everything is already organized into five numbered steps inside the config so you can see what each section does at a glance.

## Install in a Minute
1. Download or copy `autoexec.cfg`.
2. Drop it in your CS2 config folder (default: `C:\Program Files (x86)\Steam\steamapps\common\Counter-Strike Global Offensive\game\csgo\cfg\`).
3. Add `+exec autoexec.cfg` to your CS2 launch options or run `exec autoexec.cfg` once from the console.

## What You Get
- All common keyboard, mouse, UI, comms, and chat-wheel binds already defined.
- A secondary alias layer for grenade slots that you can toggle on demand.
- Clear comments inside the file so you can swap keys or actions fast.

## Step-by-Step Overview

### Step 1 – Default bindings
The file first restores a clean baseline: mouse settings, movement keys, weapons, UI, and comms. Here is a small excerpt so you know what to expect:

```cfg
bind "w" "+forward"            // Move Forward
bind "shift" "+sprint"         // Walk
bind "mouse1" "+attack"        // Fire
bind "g" "drop"                // Drop Weapon
alias PrimaryWeapon "bind 2 slot1"   // Primary Weapon
alias SecondaryWeapon "bind 3 slot2" // Secondary Weapon
```

Feel free to replace any `bind` line with your own key of choice; just keep the quotes when the key name is more than one character (for example `"mouse4"`).

### Step 2 – Secondary slot aliases
Next, each grenade slot is wrapped in an alias so it can be recalled later while the toggle is active:

```cfg
alias MolotovSlot "slot10"          // Slot10 is the Molotov
alias SmokeGrenadeSlot "slot8"      // Slot8 is the Smoke Grenade
alias FlashbangSlot "slot7"         // Slot7 is the Flashbang
alias HEGrenadeSlot "slot4"         // Slot4 is the HE Grenade
```

### Step 3 – Secondary rebind macros
These aliases temporarily remap keys `1–4` to the grenade slots above whenever the toggle is pressed:

```cfg
alias MolotovSecond "bind 1 MolotovSlot"
alias SmokeGrenadeSecond "bind 2 SmokeGrenadeSlot"
alias FlashbangSecond "bind 4 FlashbangSlot"
alias HEGrenadeSecond "bind 3 HEGrenadeSlot"
```

Change the number in `bind <number>` if you want a different key to call that utility while the toggle is held.

### Step 4 – Toggle logic
Two aliases handle the swap. Activating the toggle pushes the secondary binds; releasing it restores your normal weapon keys:

```cfg
alias +secondarycommand "MolotovSecond; FlashbangSecond; HEGrenadeSecond; SmokeGrenadeSecond"
alias -secondarycommand "PrimaryWeapon; SecondaryWeapon; MeleeWeapon; CycleGrenades"
```

Separate each alias with a semicolon, and feel free to add more commands to either list if you create extra secondary actions.

### Step 5 – Toggle key
Finally, the toggle is assigned to `mouse5` by default:

```cfg
bind "mouse5" "+secondarycommand"
```

Swap `mouse5` for any key or mouse button that feels comfortable.

## Customization Tips
- Want different utilities? Point the slot aliases in Step 2 to other actions (e.g., `slot5` for C4) or even custom scripts.
- Prefer a hold-to-toggle versus press-to-toggle? The current setup already behaves like “hold to use utilities.” Change to a true toggle by binding a key to `toggle secondarycommand` with extra logic if you need it.
- Keep related commands grouped; this makes troubleshooting easy if something stops working.

## FAQ

**What problem does this solve?** Holding the secondary key lets you reuse the familiar `1–4` keys (or any you pick) for grenades or specialty actions without permanently rebinding them.

**Why not just bind grenades to other keys?** Some players prefer to keep muscle memory on the number row and avoid accidental presses on extra keys. This method keeps the layout tidy and works well for compact or one-handed keyboards.

**Can I add custom scripts (e.g., jump-throw)?** Yes. Replace any of the secondary aliases with your own commands, or append new ones and include them inside `+secondarycommand`/`-secondarycommand`.

## Stay in Touch
If this helped, please ⭐ the repo, follow [@OhLasFar](https://twitter.com/OhLasFar), or say hi on the [link hub](https://linktr.ee/LasFar). Thanks for reading!

