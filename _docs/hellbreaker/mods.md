---
title: Mods
permalink: /docs/hellbreaker/mods/
---

If you're making a mod that extends the game, it's recommended that you keep the original game files unchanged, and put your files in a new data directory, which you can tell the game to use using the resource path [command line](https://urho3d.github.io/documentation/HEAD/_running.html#Running_Commandline) `-p` (you also need to include the game's resource paths `Data;CoreData`).
This makes adding, removing and combining mods easier.

You can also package your mod using the [Package Tool](https://urho3d.github.io/documentation/HEAD/_tools.html#Tools_PackageTool), and use it with the `-pf` command (you also need to include the game's package `DataPack.pak`).
It's recommended to use the compression option `-c` to reduce file size and loading time.

Note that resource paths and packages should have unique file paths.

### Steam Workshop

Mods can be automatically installed using [Hellbreaker's Workshop](http://steamcommunity.com/app/793620/workshop/).


#### Creating workshop item

The first step is to create a workshop item definition file.
The definition file is a [Deco](https://github.com/Enhex/Deco) text file, and it looks something like this:
```
title:
Your mod's title
:
description:
Your mod's description
:
content:
path/to/your mod content directory
:
preview:
preview image.jpg
:
```
Note:
* The content folder path is relative to the definition file.
* The preview image's format should be something that Steam accepts (example: PNG and JPG).
* Make sure your text editor uses line-feed line ending, for the Deco file to be parsed correctly.

Inside the content directory the game will look for:
* `Data` directory to add as a resource path.
* `Data.pak` to add as a resource package.
* `Levels` directory to search inside for level files.

After your mod is ready with content and a preview image, you can upload it to the workshop by drag-and-dropping the definition file onto `Game\Tool\steam_workshop.exe`, or pass to it the path to the definition file as a command line parameter.
When the workshop item is first created, a `published_file_id` entry will be added to the definition file so the item can be updated later on.

[Workshop item example](https://github.com/Enhex/Hellbreaker-Manlet-Mod).