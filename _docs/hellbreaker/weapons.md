---
title: Weapons
permalink: /docs/hellbreaker/weapons/
---

Weapons are used by the player.
They derive from the base classes `Weapon` and `WeaponTypeInfo` which are defined in `Data/Scripts/Weapon.as`. 

`WeaponTypeInfo` is used to hold and share information which is the same across all instances of a weapon class.


## Creating new weapons

You should use the weapons provided with the game as examples for implementing weapons. They can be found inside `Data/Scripts/Weapons/`.

To create a new weapon you need to create two new classes:

###### WeaponTypeInfo
The first class derives from `WeaponTypeInfo`, and defines shared information.
Read the comments in `Weapon.as` and look at weapon examples to learn what each member variable is used for.

You need to add an instance of your new `WeaponTypeInfo` derived class in the global [Dictionary](https://urho3d.github.io/documentation/HEAD/_script_a_p_i.html#Class_Dictionary) `weapon_types`. Look in the file `Data/Scripts/Weapons.as` for example.

###### Weapon
The second class derives from `Weapon`.

Override the `fire` function to define what happens when the player fires the weapon.
You can use [attacks]({{site.baseurl}}/docs/hellbreaker/attacks) from it.

The `Weapon` class comes with some utility functions like `consume_ammo` and `muzzleFlash`.
For extra weapon utlities you can use things from `Data/Scripts/WeaponUtility.as`, such as `FireCooldown_mixin` and `shoot_bullet`.

In your class's constructor you should set `Weapon::type` to the corresponding class derived from `WeaponTypeInfo` by getting it from `weapon_types`.