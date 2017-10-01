---
title: Mods
permalink: /docs/hellbreaker/mods/
---

If you're making a mod that extends the game, it's recommended that you keep the original game files unchanged, and put your files in a new data directory, which you can tell the game to use using the resource path [command line](https://urho3d.github.io/documentation/HEAD/_running.html#Running_Commandline) `-p` (you also need to include the game's resource paths `Data;CoreData`).
This makes adding, removing and combining mods easier.

You can also package your mod using the [Package Tool](https://urho3d.github.io/documentation/HEAD/_tools.html#Tools_PackageTool), and use it with the `-pf` command (you also need to include the game's package `DataPack.pak`).
It's recommended to use the compression option `-c` to reduce file size and loading time.

Note that resource paths and packages should have unique names.