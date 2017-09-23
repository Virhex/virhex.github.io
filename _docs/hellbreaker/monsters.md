---
title: Monsters
permalink: /docs/hellbreaker/monsters/
---

Monsters use the `Monster` base class, which is define in `Data/Scripts/Monster.as`.
You can find the game's monster classes scripts inside `Data/Scripts/Monsters/`.

## Monster States

Monster behavior can be in one of the following states:

##### Idle
The monster will do a line of sight check for the player in front of it. If it has line of sight it will target the player.

When idle monsters can also "hear" the player and spot him, using the function `hearSound`.
Monsters can also be set to be deaf with the variable `deaf`.


##### Move
The monster will move in random direction baised towards its target.
When it has line of sight on its target it has a random chance to start an attack that increases as it gets closer to its target.

Additionally when the monster starts moving, if it's within `instant_attack_range` distance from the target, it will instantly start an attack.


##### Attack
The monster will target either the player or whoever damages it.
Monsters of the same type can't damage each other.
If the monster doesn't have line of sight of its target for long enough, it will go back to idle state.

After its target dies the monster will go back to idle state, unless it already spotted the player, in which case it will target the player.

The function `choose_attack` is used to select which attack the monster will use (for example melee or ranged).
Inside the function you can set several options:
- `continue_attacking` is used to tell the monster if to immediately start another attack after this attack ends if `true`, or start moving if `false`.
- `cancel_attack` is used to cancel the attack by setting it to `true`.

When the monster starts attacking it will play its attack animation. [Animation trigger](https://urho3d.github.io/documentation/HEAD/_skeletal_animation.html#SkeletalAnimation_Triggers) can be used to decide when to execute `attack_callback` with trigger value `"attack"`, and when to end the attack with trigger value `"end"`.
If you use animation trigger you must set `attack_callback` inside `choose_attack`. `attack_callback` is a `ATTACK_CALLBACK` [funcdef](http://www.angelcode.com/angelscript/sdk/docs/manual/doc_global_funcdef.html).

Alternatively you can set `use_attack_duration` to `true` and set `attack_duration` to how long the attack should last.
This approach doesn't use `attack_callback`. Instead you can override `attack_update` which will be called every fixed update while attacking.

`attack_end` is called when the attack ends.

You can use things from [Attacks]({{site.baseurl}}/docs/hellbreaker/attacks) for your monster attacks.


##### Flinch
Flinching will interrupt the monster's movement and attack.
When the flinch ends the monster will start moving.

When a monster takes damage, it has a chance to flinch.
`flinch_chance` is the chance variable, and its value should be in the range [0,1].

Flinching lasts for the duration set in `MonsterType::flinch_duration`.


## Creating new monsters

##### Existing behavior
You can create new variation of an existing monster by copying its node object and editing its properties.
can use the [game editor]({{site.baseurl}}/docs/hellbreaker/game-editor) for that.
The game's monster node object files are inside `Data/Objects/Monster/`.


##### New behavior

You can create new monster behavior

###### MonsterType
`MonsterType` holds information that is the same across all instances of the monster class, for example animations and sounds.

You need to create a new `MonsterType` instance using the function `game.levelInfo.add_monster_type` and set its variables.
The game does that for its monsters inside a function, and calls all those monster type functions in the function `RegisterMonsters` which is defined in `Data/Scripts/Monsters.as` and called when the level starts.

###### Monster
Derive your new monster class from `Monster`. `MonsterFly` is also available.

In your class's constructor set `Monster::type` to your `MonsterType` using the function `game.levelInfo.get_monster_type`.

From here you're free to do anything. Look at the game's monster scripts for examples of how monsters can be implemented.
