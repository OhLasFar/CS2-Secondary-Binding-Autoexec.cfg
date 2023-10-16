
# Introduction
This guide is an auto-exec that includes ALL of the default bindings, including the possibility of having secondary bindings.
It is important to follow along, as one mistake could ruin the entire configuration.
Any modifications to the file are possible, and I've tried to explain them as best as I can so you don't get lost during the process.
Please consider giving it a star, and a follow on Twitter @OhLasFar would be greatly appreciated.

In this guide you will find 5 steps, theses steps are also writen and easily foundable in the autoexec.cfg file.

# STEP 1 : SET DEFAULT BINDINGS

You will have to bind all of your keys that you usually use and make sure to bind them correctly with the correct key.

| Command       | Key           | Action        | Comment (Not necessary) |
| ------------- | ------------- | ------------- | ----------------------- |
| bind          | g             | drop          | // Drop Weapon          |
| bind          | f             | +lookatweapon | // Inspect Weapon       |


So in your autoexec.cfg you would get something like this ;
```
bind g drop							// Drop Weapon
bind f +lookatweapon						// Inspect Weapon
```
⚠️ Please note that keybinding letters must ALWAYS be set in lowercase.

# STEP 2 : ALIASES CREATION AND THEIR PURPOSE

In step two, you will need to create new values for your future secondary keybinds actions. It's important to know that your aliases name must be DIFFERENT so for example, you cannot use MolotovSlot two times in two different part BUT step 4.

| Macro   | Alias Name       | Action       |
| ------- | ---------------- | ------------ |
| alias   | MolotovSlot      | slot10       |
| alias   | FlashbangSlot    | slot7        |
| alias   | HEGrenadeSlot    | slot4        |
| alias   | SmokeGrenadeSlot | slot8        |

If you are unsure of wich action you can use, you can find all the available action that you can use in C:\Program Files (x86)\Steam\steamapps\common\Counter-Strike Global Offensive\game\csgo\cfg\user_keys_default.vcfg
Be careful the action will always equal to the binding next to it even if you do the command unbindall. Actions can be found to the right.
```
"config"
{
	"bindings"
	{
...
		"8" 			"slot8"
		"9" 			"slot9"
		"a" 			"+left"
		"b" 			"buymenu"
		"c" 			"+radialradio"
...
	}
}
```

# STEP 3 : SET SECONDARY KEY BINDINGS

In step 3 you will have to create your aliases name and tell them what they bind to. So for example, the alias name binds to the full console command "bind 1 MolotovSlot". 

Please note that for the full console command this symbol " is needed in order to work properly.
| Macro   | Alias Name          | Full Console Command      |
| ------- | ------------------- | ------------------------- |
| alias   | MolotovSecond       | "bind 1 MolotovSlot"      |
| alias   | FlashbangSecond     | "bind 4 FlashbangSlot"    |
| alias   | HEGrenadeSecond     | "bind 3 HEGrenadeSlot"    |
| alias   | SmokeGrenadeSecond  | "bind 2 SmokeGrenadeSlot" |

Step 3 is for when you press on the key that you will bind in part 5, it will basically bind theses new keybinds to your keys. Alternatively, it would also be possible to use for example "MolotovSecond" in the console and it would execute "bind 1 MolotovSlot"

# STEP 4 : TOGGLE LOGIC

In step 4, this is the toggle logic for activating your Seconday bindings and the auto deactivation when the button is released.

In the alias +secondarycommand, it is important to add or remove ANY aliases that you have set in Part 3. After every aliases you must always add a ";" but NOT for the last alias.
In the alias -secondarycommand, it is important to add or remove ANY aliases that you have set in Part 1 as this will allow you to get back your main keybinds after releasing the button that will be set in Part 5.
| Macro   | Alias Name          | Full Console Command                                                   |
| ------- | ------------------- | ---------------------------------------------------------------------- |
| alias   | +secondarycommand   | "MolotovSecond; FlashbangSecond; HEGrenadeSecond; SmokeGrenadeSecond"  |
| alias   | -secondarycommand   | "PrimaryWeapon; SecondaryWeapon; MeleeWeapon; CycleGrenades"           |

# STEP 5 : SECONDARY KEYBINDS TOGGLE

In step 5, this is the final step. You will need to bind your wanted key and you will be able to toggle your secondary keybinds.
When pressing down your key, this will activate +secondarycommand and upon release, it will then activate -secondarycommand

| Command       | Key           | Action            |
| ------------- | ------------- | ----------------- |
| bind          | mouse5        | +secondarycommand |
