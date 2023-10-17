
# Introduction

Welcome to this guide! It covers how to set up your new auto-exec with ALL default bindings and even add secondary ones. Follow closely! A small mistake could mess things up. But don't worry; I've explained each step clearly. If you find this guide helpful, please give it a star. And hey, a follow on Twitter @OhLasFar would make my day!

The guide is divided into 5 easy-to-follow steps. You can find these steps labeled in the `autoexec.cfg` file too.

Additionally, it's crucial to integrate or merge your `autoexec.cfg` into the specified path: `C:\Program Files (x86)\Steam\steamapps\common\Counter-Strike Global Offensive\game\csgo\cfg\`.

# Step 1: Setting Default Key Bindings

Set up your primary key bindings using the following alias commands. These commands ensure you can quickly revert to your original bindings after using the secondary keybinds and are crucial for the secondary bindings to function as expected.
```
alias PrimaryWeapon "bind 2 slot1"       // Primary Weapon 
alias SecondaryWeapon "bind 3 slot2"     // Secondary Weapon 
alias MeleeWeapon "bind 1 slot3"         // Melee Weapon 
alias CycleGrenades "bind 4 slot4"       // Cycle Grenades 
```

If you decide to change or remove an alias, like `PrimaryWeapon`, you can directly use `bind 2 slot1` instead of `alias PrimaryWeapon "bind 2 slot1"`. It'll function normally. However, if you adjust or remove the alias here, ensure to also modify it in Step 4.

After setting these aliases, bind the keys you use regularly. Ensure each key is matched to its intended action.

For example:
| Command       | Key           | Action        | Comment (Not necessary) |
| ------------- | ------------- | ------------- | ----------------------- |
| bind          | g             | drop          | // Drop Weapon          |
| bind          | f             | +lookatweapon | // Inspect Weapon       |


In `autoexec.cfg`, it should look like:
```
...
alias PrimaryWeapon "bind 2 slot1"      // Primary Weapon 
alias SecondaryWeapon "bind 3 slot2"    // Secondary Weapon 
...
bind g drop				// Drop Weapon
bind f +lookatweapon			// Inspect Weapon
...
```
⚠️ Remember: always use lowercase for keybinding letters.

# Step 2: Creating Aliases for Secondary Keybinds

Create aliases for your secondary keybind actions. __Make sure each alias name is unique!__

For instance:
| Macro   | Alias Name       | Action       |
| ------- | ---------------- | ------------ |
| alias   | MolotovSlot      | slot10       |
| alias   | FlashbangSlot    | slot7        |
| alias   | HEGrenadeSlot    | slot4        |
| alias   | SmokeGrenadeSlot | slot8        |

Not sure about available actions? Check out the file at:
`C:\Program Files (x86)\Steam\steamapps\common\Counter-Strike Global Offensive\game\csgo\cfg\user_keys_default.vcfg`

💡 Actions can be found to the right in this file and be careful the action will always equal to the binding next to it even if you do the command unbindall. 


# Step 3: Setting Up Secondary Key Bindings

Assign actions to your aliases. For instance, the alias "`MolotovSecond`" links to the command "`bind 1 MolotovSlot`".

Note: Always use quotation marks (" ") for full console commands.
| Macro   | Alias Name          | Full Console Command      |
| ------- | ------------------- | ------------------------- |
| alias   | MolotovSecond       | "bind 1 MolotovSlot"      |
| alias   | FlashbangSecond     | "bind 4 FlashbangSlot"    |
| alias   | HEGrenadeSecond     | "bind 3 HEGrenadeSlot"    |
| alias   | SmokeGrenadeSecond  | "bind 2 SmokeGrenadeSlot" |

This step ensures that when you press your binded key (defined in Step 5), it will reassign new functions to your keys.

# Step 4: Toggle Logic

This step covers the logic to switch between primary and secondary keybinds.

For activation:
| Macro   | Alias Name          | Full Console Command                                                   |
| ------- | ------------------- | ---------------------------------------------------------------------- |
| alias   | +secondarycommand   | "MolotovSecond; FlashbangSecond; HEGrenadeSecond; SmokeGrenadeSecond"  |

For deactivation:
| Macro   | Alias Name          | Full Console Command                                                   |
| ------- | ------------------- | ---------------------------------------------------------------------- |
| alias   | -secondarycommand   | "PrimaryWeapon; SecondaryWeapon; MeleeWeapon; CycleGrenades"           |

💡 Always separate commands with a semicolon (;) but skip it for the last command.
Note: When using the PrimaryWeapon alias (or any other alias), it's equivalent to manually entering the command "bind 2 slot1" in the game console.

# Step 5: Toggle Secondary Keybinds

Lastly, bind a key to toggle between the primary and secondary commands.

| Command       | Key           | Action            |
| ------------- | ------------- | ----------------- |
| bind          | mouse5        | +secondarycommand |

Pressing this key activates your secondary keybinds, and releasing it goes back to primary ones.

# 🌟 Thanks for Making It This Far! 🌟

I truly appreciate you taking the time to read through this documentation. If you found it helpful, please consider leaving a ⭐ star. It means a lot!

🌐 For more updates and cool stuff, don't hesitate to [follow me on my socials](https://linktr.ee/LasFar).

🎁 Feeling generous? You can [trade with me on Steam](https://steamcommunity.com/tradeoffer/new/?partner=325412381&token=RI4Jz8Ya) or if you'd like to [buy me a coffee](https://botrix.live/y/@lasfar/tip), I'll give you a special shoutout on my next stream. Every bit helps, and I'm grateful for your support!

Stay awesome and stay safe! ❤️
