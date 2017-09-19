---
title: Pickups
permalink: /docs/hellbreaker/pickups/
---

Pickups are special objects that trigger when the player touches them.

The `Pickup` base class is located at `Data/Scripts/Pickup.as`.
Pickups classes that derive from it should be located inside the directory `Data/Scripts/Pickups/`, where you can find the pickup classes that come with the game (health, ammo, weapon, etc).

## Creating new pickups

You can create new pickups with different parameters for existing behavior by creating new node objects. for that use the [game editor]({{site.baseurl}}/docs/hellbreaker/game-editor).

If you want to create a pickup with new behavior, you need to create a new script that inherits from the class `Pickup` and implements that behavior.

TODO: Make sure your new script is included

TODO:
- when adding a new pickup file it needs to be included into Main.as