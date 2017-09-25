---
title: Game Content
permalink: /docs/hellbreaker/content/
---


## Resources Overview

The `Data` directory contains game resources such as textures, models, sounds, scripts, and so on.
Directories inside `Data` have self-explanatory names for the kind of resource they contain.

Some of the assets are packed away inside `DataPack.pak`. You can read the files paths of the files inside it from `DataPackTree.txt`.

Textures are images used for rendering. The game supports image formats such as `PNG`, `JPEG`, `TGA`, `GIF`, `DXT1/3/5`, and more.

Materials define how geometry is rendered. Materials may use textures. [Urho3D Material documentation](https://urho3d.github.io/documentation/HEAD/_materials.html).

Models define 3D geometry. Models use materials.

For more information about resources see [Urho3D Resources documentation](https://urho3d.github.io/documentation/HEAD/_resources.html).


## Scene Overview

The game uses a scene graph. The scene is made up of hierarchy of nodes, starting from the scene's root node.
Each node can have child nodes and compontents, and has transformation: position, rotation, and scale.
Components are things like models, sound sources, physical bodies, and lights.

You can learn about the available components from [Urho3D's documentation](https://urho3d.github.io/documentation/HEAD/index.html). For example [Rendering components](https://urho3d.github.io/documentation/HEAD/_rendering.html#Rendering_Drawable).

For example, if you want to display a 3D model, you need to create a node and set its desired transformation, and create a [StaticModel](https://urho3d.github.io/documentation/HEAD/class_urho3_d_1_1_static_model.html) component with the model you want to display as a child of that node.

Nodes can be saved, including all their child nodes/components, as "Objects". You can use the [game editor]({{site.baseurl}}/docs/hellbreaker/game-editor) to edit and create node objects.

For more information see [Urho3D Scene model documnetation](https://urho3d.github.io/documentation/HEAD/_scene_model.html).


## Importing Assets

Urho3D uses its own `.mdl` 3D model file format. You'll need to convert models to Urho3D's format to use them.

###### [Urho3D's AssetImporter](https://urho3d.github.io/documentation/HEAD/_tools.html#Tools_AssetImporter)

A command line tool that can import from many 3D file formats.

###### [Urho3D Addon](https://github.com/reattiva/Urho3D-Blender) for [Blender](https://www.blender.org/)

Import models via Blender.

When exporting geometries, make sure that `Position`, `Normal`, `UV`, and `Tangent` options are checked.


## Levels

The `Levels` directory contains the level files. The game will recursively search inside it for compiled level files (`.clvl`).

The [level editor]({{site.baseurl}}/docs/level-editor) is used to edit and create levels.
It can opened from the launcher or `LevelEditor.exe` located inside the `Editor` directory next to the `Game` directory (not the one inside it).


## Special directories

Images inside `Data\Textures\UI` will automatically have mipmapping disabled.

Textures inside `Data\Textures\Level` will automatically have meterial generated for them using the [material creator]({{site.baseurl}}/docs/material-creator).