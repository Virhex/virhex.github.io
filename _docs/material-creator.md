---
title: Material Creator
permalink: /docs/material-creator/
---

The material creator automatically creates a material for textures using naming convention.

Given a textures folder, it recusively searches it for textures to match up into a material.

Generated materials are handled as if they had a file path relative to a given materials output directory, and use the diffuse texture's name without the suffix and file extension.

The default texture type naming convention is:
- `_D` suffix for diffuse
- `_N` suffix for normal
- `_S` suffix for specular
- `_E` suffix for emmisive

For example, if the material creator finds files `wall_D.tga`, `wall_N.tga`, `wall_S.tga` inside the same folder, it will generate a material for them using `DiffNormalSpec` technique.

Only diffuse texture is mandatory, the rest are optional.

Diffuse and emissive textures can have variation, that will use the same normal and specular textures.
Variation naming convention is `_[N]` suffix before the texture type suffix, where `[N]` is the variation number, starting from 0. For example `wall_0_D.tga`.

If a file doesn't match the naming convention, it's assumed as a diffuse texture.

The material creator also detect alpha in the diffuse texture, and if found uses alpha masking for the material.

You can replace a generated material with your own custom material by placing your material file at the file path the generated file would have.

For example: if `Textures/` is the material creator's textures directory, and `Materials/` is the output directory, 
you can provide your own material for texture `Textures/Floors/floor.tga` by placing your file at `Materials/Floors/floor.xml`.