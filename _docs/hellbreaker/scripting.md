---
title: Scripting
permalink: /docs/hellbreaker/scripting/
---

Hellbreaker's scripting uses the AngelScript scripting language, and is built on top of Urho3D's API.
AngelScript is a statically typed and compiled language, similar to C++/C#.

You can learn more about AngelScript from [AngelScript's language documentation](http://www.angelcode.com/angelscript/sdk/docs/manual/doc_script.html).

Urho3D's scripting API:
- [Urho3D scripting API](https://urho3d.github.io/documentation/HEAD/_script_a_p_i.html)
- [Urho3D scripting documentation](https://urho3d.github.io/documentation/HEAD/_scripting.html)

You should know how to program, this is not a programming tutorial.

You should actively look at the game's script code when learning to see concrete examples.


### Entry Point
The script entry point is the `Main` class, which can be found in `Data/Scripts/Main.as`.
The game script is executed when a level is loaded.


### The Player

The `Player` class inherits from `Destructible`, which inherits from `Damageable`.

`Damageable` is used for things that can take damage.

`Destructible` is used for things that also have health and can die.

You can get the player's inventory via `Player::inventory()`.
The inventory is a map from item names to item amounts. The game uses it for items like weapon ammo and door keys, and it can be used for other things too.
It has the following functions:
- `uint[] item` access an item by its name
- `void add_item(const String& item_type, const int amount)` to add to the amount of an item

`Player` also have `WeaponSlots` member, which contains the player's weapons.
There are 0 to 9 available slots, and weapons that occupy the same slot are ordered by their position value.


## Script Modules

Each script file used by [ScriptInstance](https://urho3d.github.io/documentation/HEAD/class_urho3_d_1_1_script_instance.html) is a separate [script module](http://www.angelcode.com/angelscript/sdk/docs/manual/doc_module.html).
Modules dont share code, except things that are declared [shared](http://www.angelcode.com/angelscript/sdk/docs/manual/doc_script_shared.html), in which case it should only be defined once (don't include it several times).

The game uses a single script module. The scene's root node holds the `Main.as` script instance.
Any script that interacts with things from the main module should be part of it.
Only if script are completely indepenent of the main module they can be used in a separate script module.


## Editing script files

[Atom](https://atom.io/) is an open source text editor that has [AngelScript syntax highlighting package](https://atom.io/packages/language-angelscript).