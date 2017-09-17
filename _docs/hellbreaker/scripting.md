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


### Entry Point
The script entry point is the Main class, which can be found in `Data/Scripts/Main.as`.
It's executed when a level is loaded.


### The Player

Damageable -> Destructible

Button that is triggered by damage

TODO:
- items inventory
- weapons