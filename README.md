# Persona 5 RPCS3 Mods

A tiny collection of Persona 5 mods for the Sony PlayStation 3 emulator [RPCS3](https://rpcs3.net/).

## Disclaimer

I wrote and tested these mods back in 2020 and haven't touched them since. I haven't personally experienced any crashes or bugs while using these, but I am not responsible if something does happen. If you encounter problems, please file an issue.

Have fun!

## List

### [Replace Igor With the Principal](./replace-igor-with-principal/imported_patch.yml)

Replaces Igor's character model with that of the Principal.

### [Everyone is the Principal](./everyone-is-the-principal/imported_patch.yml)

Replaces all character, persona, and enemy models with that of the Principal.

## Installation

Copy the `imported_patch.yml` file from the directory of the desired mod to the `patches/` folder within your RPCS3 installation. Then, navigate to the *Manage > Game Patches* page in RPCS3, open the *Persona 5* tab, check the desired mod, and click *Apply*.

See the [relevant RPCS3 Wiki page](https://wiki.rpcs3.net/index.php?title=Help:Game_Patches#Manually_adding_custom_patches) for more information.

## How Do These Mods Work? Or, How Can I Create My Own Mods?

I disassembled the game binary, sifted through strings until I found code related to model-loading, and traced the control flow from there so that I could understand how it works. I learned that Persona 5 loads character models from files with the extension `.GMD`. I then extracted these `.GMD` files from the game binary and identified which filenames corresponded to Igor and the Principal. From there, I patched the model-loading code to replace instances of other model filenames with that of the Principal; in the case of *Replace Igor With the Principal*, I only replaced the filename of Igor's model, while for *Everyone is the Principal* I hardcoded the model-loading code to always load the Principal's file.

I might add more instructive comments to the patches eventually. Feel free to email me if you have any questions, though I can't guarantee I will remember how I did everything.
