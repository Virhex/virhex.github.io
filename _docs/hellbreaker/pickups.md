---
title: Pickups
permalink: /docs/hellbreaker/pickups/
---

Pickups are special objects that trigger when the player touches them.

The `Pickup` base class is defined in `Data/Scripts/Pickup.as`.
Game pickup classes that derive from it are located at `Data/Scripts/Pickups/` (health, ammo, weapon, ...).


## Creating new pickups

##### Existing behavior
You can create new pickups with different parameters for existing behavior by creating new node objects.
You can use the [game editor]({{site.baseurl}}/docs/hellbreaker/game-editor) for that.
The node object should have a `RigidBody` component, and a `ScriptInstance` component that uses `Main.as` as the script file, and the class of the pickup you want to use. You can look at existing pickup node objects for example, they're located at `Data/Objects/Pickup/`.

##### New behavior
If you want to create a pickup with new behavior, you need to create a new pickup class that inherits from the class `Pickup`.

`bool onPickup()` will be called when the player collides with the pickup. Override it and specify what will happen. Return `true` if picking up was secessful and the pickup should be removed, or `false` so it won't be removed. For example `PickupHealth` returns `false` if the player already has full health.

You need to include your new script files into `Main.as` script module, so the game will know about your classes.