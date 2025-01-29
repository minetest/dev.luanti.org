# Light - Luanti Wiki


In Luanti, **light** is entirely block-based, just like the rest of the world.

Light level
-----------

As the world is entirely block-based, so is the light in the world. Each block has its own brightness.

The brightness of a block is expressed in a “light level” which ranges from 0 (total darkness) to 15 (as bright as the sun).

Types of light
--------------

There are two types of light: Sunlight and artificial light.

### Artificial light

Artificial light is emitteed by luminous blocks. Artificial light has a light level from 1-14.

### Sunlight

Sunlight is the brightest light and always goes perfectly straight down from the sky at each time of the day. blocks. At night, the sunlight will become moonlight instead, which still provides a small amount of light. The light level of sunlight is 15.

Light transparency
------------------

Blocks have 3 levels of transparency to light/brightness:

*   Transparent: Sunlight goes through limitless, artificial light goes through with losses
*   Semi-transparent: Sunlight and artificial light go through with losses
*   Opaque: No light passes through

Artificial light will lose one level of brightness for each transparent or semi-transparent block it passes through, until only darkness remains. Sunlight will preserve its brightness as long it only passes fully transparent blocks. When it passes through a semi-transparent block, it turns into artificial light.

Note that “transparency” here does not always mean you can see through a block. It only means that the block is able to carry brightness from its adjacent blocks.

Light in Minetest Game
----------------------

### Examples for transparent blocks

*   [Air](https://wiki.luanti.org/Air "Air")
*   [Glass](https://wiki.luanti.org/Glass "Glass")
*   [Obsidian Glass](https://wiki.luanti.org/Obsidian_Glass "Obsidian Glass")
*   A few small plants

### Examples for semi-transparent blocks

*   [Water](https://wiki.luanti.org/Water "Water"), [River Water](https://wiki.luanti.org/River_Water "River Water") and [Lava](https://wiki.luanti.org/Lava "Lava")
*   [Leaves](https://wiki.luanti.org/Leaves "Leaves") and the like
*   [Fences](https://wiki.luanti.org/Fence "Fence") and the like
*   [Ice](https://wiki.luanti.org/Ice "Ice")
*   [Mese Block](https://wiki.luanti.org/Mese_Block "Mese Block")
*   [Slabs](https://wiki.luanti.org/Slab "Slab") and [Stairs](https://wiki.luanti.org/Stair "Stair")
*   [Doors](https://wiki.luanti.org/Door "Door"), [Trapdoors](https://wiki.luanti.org/Trapdoor "Trapdoor") and the like
*   A few other small plants

### Examples for opaque blocks

*   [Stone](https://wiki.luanti.org/Stone "Stone")
*   [Wooden Planks](https://wiki.luanti.org/Wooden_Planks "Wooden Planks")

See also
--------

*   [Luminous blocks](https://wiki.luanti.org/Category:Luminous "Category:Luminous")
*   [Time of day](https://wiki.luanti.org/Time_of_day "Time of day")
