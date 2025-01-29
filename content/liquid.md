# Liquid - Luanti Wiki


**Liquids** are special dynamic [blocks](https://wiki.luanti.org/Block "Block") in Luanti. They behave quite differently than in real life. Liquids like to spread and flow to their surrounding blocks and players can swim and drown in them.

Liquid forms
------------

Liquids usually come in two forms: In source form and in flowing form.

### Liquid source

Liquid sources have the shape of a full cube. A liquid source will generate flowing liquids around it from time to time, and, if the liquid is renewable, it also generates liquid sources (see below). A liquid source can sustain itself. If no special event happens, a liquid source will keep its place forever and it will never drain out.

### Flowing liquid

Flowing liquids take a “sloped” form and never the shape of a cube. Flowing liquids spread around the map until they drain. A flowing liquid can not sustain itself and always comes from a liquid source, either directly or indirectly. Without a liquid source, a flowing liquid will eventually drain out and disappear.

Liquid properties
-----------------

[![](https://wiki.luanti.org/images/thumb/2/2d/Liquid_range_2.png/170px-Liquid_range_2.png)](https://wiki.luanti.org/File:Liquid_range_2.png)

A liquid with a flowing range of 2, viewed from above

All liquids share the following properties:

*   _All properties of [blocks](https://wiki.luanti.org/Blocks "Blocks")_
*   Renewability: Renewable liquids can create new sources (see below)
*   Flowing range: How many flowing liquids are created at maximum per liquid source, it determines how far the liquid will “spread”. This is a number ranging from 0 to 8. If 0, no flowing liquids are generated at all. Usually, liquids have a flowing range of 8
*   Viscosity: How slow [players](https://wiki.luanti.org/Player "Player") move through it and how fast new flowing liquids are created (i.e. how fast the liquid spreads)
*   Drowning damage: If set, it will a) reduce your [breath](https://wiki.luanti.org/Player#Breath "Player") (“bubbles”) while you are inside and b) will cause this amount of damage to you every 2 seconds if you ran out of breath while inside

Behaviour
---------

### Creation of liquid sources

Renewable liquid sources create new liquid sources at open spaces. A new liquid source is created when:

*   Two renewable liquid blocks of the same type touch each other diagonally
*   These blocks are also on the same height
*   One of the two “corners” is open space which allows liquids to flow in

When those criteria are met, the open space is filled with a new liquid source of the same type.

*   [![](https://wiki.luanti.org/images/thumb/5/59/Liquid_renewing_part1.png/350px-Liquid_renewing_part1.png)](https://wiki.luanti.org/File:Liquid_renewing_part1.png)
    
    2 liquid sources (S) touch each other diagonally, but are seperated by solid blocks.
    
*   [![](https://wiki.luanti.org/images/thumb/3/39/Liquid_renewing_part2.png/350px-Liquid_renewing_part2.png)](https://wiki.luanti.org/File:Liquid_renewing_part2.png)
    
    The solid block at the top “corner” has been removed and a completely new liquid source block fills the empty space shortly after.
    
*   [![](https://wiki.luanti.org/images/thumb/a/af/Non-renewable_liquid.png/350px-Non-renewable_liquid.png)](https://wiki.luanti.org/File:Non-renewable_liquid.png)
    
    For comparison, a non-renewable liquid just flows (F) instead.
    

Interaction with liquids
------------------------

### Swimming and diving

Swimming in a liquid is fairly straightforward: The usual direction keys for basic movement, the jump key for rising and the sneak key for sinking. Note that the controls are different if the [pitch move mode](https://wiki.luanti.org/Controls#Pitch_move_mode "Controls") is enabled.

The physics for swimming and diving in a liquid are, in detail:

*   Your movement speed in a liquid is determined by its viscosity
*   If you don't do anything in a liquid, you will slowly sink
*   There is no fall damage for falling into a liquid as such
*   If you fall from a great height into a liquid, you will be slowed down on impact (but you don't come instantly to a halt). Depending on your speed, you might end up deep in the liquid. The slow-down effect is much stronger for liquids with a high viscosity. For a safe high drop into a liquid, you need to make sure there is enough liquid above the ground, otherwise you might still suffer fall damage by hitting the ground.
*   Liquids may cause breath loss and drowning damage (see above)

### Pointing to liquids

Liquids are usually not [pointable](https://wiki.luanti.org/Pointing "Pointing"). However, all liquids can be pointed by special items. In [Minetest Game](https://wiki.luanti.org/Games/Minetest_Game "Games/Minetest Game"), one example is the [bucket](https://wiki.luanti.org/Bucket "Bucket"). For a full list of items which are able to point to liquids, see [Category:Liquid pointers](https://wiki.luanti.org/Category:Liquid_pointers "Category:Liquid pointers").

Liquids in [Minetest Game](https://wiki.luanti.org/Games/Minetest_Game "Games/Minetest Game")
---------------------------------------------------------------------------------------------

The following liquids exist in Minetest Game:


|   |Liquid     |Renewable[1]|Flowing range|Viscosity|Drowning damage|
|---|-----------|------------|-------------|---------|---------------|
|   |Water      |Yes         |8            |1        |               |
|   |River Water|No[2]       |2            |1        |               |
|   |Lava       |No          |8            |7        |               |


1.  [↑](#cite_ref-1) Renewable according to the method explained above
2.  [↑](#cite_ref-2) Note that river water can be renewed by a different method, however

Quick facts:

*   Liquids can be collected by a [bucket](https://wiki.luanti.org/Bucket "Bucket").
*   Liquids can flow into and destroy [snow](https://wiki.luanti.org/Snow "Snow").
*   Lava will be cooled into [obsidian](https://wiki.luanti.org/Obsidian "Obsidian") or [stone](https://wiki.luanti.org/Stone "Stone") by [water](https://wiki.luanti.org/Water "Water"), [river water](https://wiki.luanti.org/River_Water "River Water"), and [other blocks](https://wiki.luanti.org/Category:Cools_lava "Category:Cools lava").