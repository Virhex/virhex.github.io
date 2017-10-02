---
title: Content
permalink: /docs/level-editor/content/
---

The level editor uses the game engine [Urho3D](https://urho3d.github.io/documentation/HEAD/index.html), so it uses Urho3D resources such as models and materials.

### Entities
Entity types are defined using a defitions file. The definition describes things like what properties the entity has and how it's represented in the editor.
The game config file describes where the entity definition files are.

### Textures
Texture search paths are set in the game config file.

### Materials
The level editor automatically generates materials for textures using the [material creator]({{site.baseurl}}/docs/material-creator) into a directory defined in the game config file.

### Objects
Automatically creates an entity for Urho3D node objects.
Automatically strips any non-graphical components from the node object.
Node object `.xml` files are search in directories set in the game config file.