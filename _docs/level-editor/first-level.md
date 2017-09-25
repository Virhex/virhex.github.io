---
title: Creating Your First Level
permalink: /docs/level-editor/first-level/
---

##### Build a room
Open the level editor.
After you've opened the level editor `Shape Tool` will be selected by default.
We're going to use it to create a shape.

In the top left grid view, press and hold the `Left mouse button` and drag a box, and then release the button.
After you set the initial box you can adjust its position by pressing and holding the `Left mouse button` inside it and dragging, or resize it by dragging the resizing handles.

At the left side of the editor you should have an `Assets` menu with materials in it. You can use it to select the material of the shape we're about to create.

After you're done adjusting your box, press `Enter` while hovering one of the views to create a shape from the box.
Try finding it in the 3D view to see how it looks like.

Create more shapes until you have a room. Use the different grid views to create floor and walls.


##### Create entities
After we've created a room from shapes, we want to put some things inside it using entities.

We'll start by telling the game where the player will start when the level starts.
Select the `Entity Tool`. in the `Assets` menu look for an entity called `player_start` (you can use the search box).

in the views you should have green cross, which represent where the entity will be created.
Click on the grid views to position the green cross on the floor inside your room, where you want the player to start.

When you're done positiong the entity position, press `Enter` while hovering one of the views to create the selected entity.

Next we want to light up the level.
Just like we created `player_start`, create a `zone` entity.
It doesn't matter where you position it, but keep it at a place which is easy to find.
`zone` can be used to set ambient light level, which we're about to do.
Switch to the `Selection Tool`, and select the `zone` entity if it isn't already selected.
In the right side of the editor, in the `Tool Options` menu, under the `Entity` section you'll have a list of the entity's properties.
Try editing the `Ambient Color` property. After you're done, press the `Apply` button at the bottom of the properties list.

Next create a `skybox` entity, just like the other entities.
Skybox is like a 3D background for the game, usually used for the game's sky (hence the name skybox).

Now lets add a monster to the level.
Select the `Object Tool`, and in the `Assets` menu select `Monster/Undead`.
Position the green cross on the floor where you want the player to be, and press `Enter` while hovering one of the views to create the monster.

You can place weapons and ammo the same way you placed a monster.
Try placing `Pickup/Shotgun`, and `Pickup/ShellsBox` in your level.

To play the level you need to compile it. Click the `Compile` button.
If the level wasn't saved yet you'll be asked to save it first.
Save your level file inside the game's levels folder.

You're done making your first level!
Now it should be available in the game, try playing it!