---
title: Attacks
permalink: /docs/hellbreaker/attacks/
---

The game provides some simple high level API for creating attacks.
You're also free to create your attacks.


## Instant attacks

Attacks that instantly apply damage. You can find some useful functions inside `Data/Scripts/Attacks.as`:
- `fire_ray` - A "hitscan" raycast that damages `Damageable`s.
- `fire_bullet` - Builds on top of `fire_ray` and adds some effects like impact puff & sparks, bullet hole, and blood splats.
- `damage_sight_sphere_linear` - Damage Damageables inside the sphere which have line of sight to the center of it, by an amount linearly relative to their distance from the sphere's center, and creates some effects.


## Projectile attacks

The game provides a projectile design in which the projectile class triggers a callbacks.
This decoupling allows the users of the class to do different things upon triggering without having to create new projectile class for each case.

New projectiles should derive from the base class `Projectile` which is defined in `Data/Scripts/Projectile.as`.

Projecile classes should only define when the projectile is triggered, not what happens when it's triggered.
Projectiles are "triggered" by calling the function `Projectile::trigger`, which will call the callback.

After creating a projectile you should set `Projectile::callback`, which is a `PROJECTILE_CALLBACK` [funcdef](http://www.angelcode.com/angelscript/sdk/docs/manual/doc_global_funcdef.html) (defined in `Projectile.as`), to point to a function.
The game provides some common functions you can use inside a callback in `Data/Scripts/ProjectileCallback.as`, such as `damage` and `explode`.

The game also provide functions for easily creating projectiles such as `fire_projectile` in `Data/Scripts/Attacks.as`.