---
title: Pickups
permalink: /docs/hellbreaker/pickups/
---

Pickups are special objects that trigger when the player touches them.

The `Pickup` base class is located at `Data/Scripts/Pickup.as`. Pickups classes that derive from it are located inside the folder `Data/Scripts/Pickups/`.

There are some other base classes that derive from `Pickup`:
- `PickupItem` - 
- `PickupItemOnce` - Checks if an item is already in the player's inventory before picking it up

TODO:
- when adding a new pickup file it needs to be included into Main.as