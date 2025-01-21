# Unknown Object - Luanti Wiki



|Unknown Object     |   |
|-------------------|---|
|                   |   |
|An object in Luanti|   |
|Health             |   |
|Object collision   |No |
|Block collision    |No |
|Entitystring       |N/A|


An **unknown object** is pseudo-[object](https://wiki.luanti.org/index.php?title=Object&action=edit&redlink=1 "Object (page does not exist)") in Luanti to represent an object (such as a [mob](https://wiki.luanti.org/Mobs "Mobs")) of which the object definition is unknown. These objects must never appear in the game, it's always an error when you encounter one.

Behaviour
---------

An unknown object appears as a flat texture with “unknown object” written on it. The velocity of the original object is usually preserved so unknown objects often tend to fly through the world.

Internally, an unknown object still knows the “real” object it represents and the associated data. You can see its entity/object ID by [pointing](https://wiki.luanti.org/Pointing "Pointing") it. If an unknown object is found by Luanti, there will also be an error message complaining about that a LuaEntity could not be found (this “LuaEntity” refers to the unknown object), along with its entity ID.

To fix problems with unknown objects, first check the troubleshooting section. Unknown objects are destroyed when punching or if they receive any amount of damage.

Troubleshooting
---------------

A common reason for an unknown object to appear is when you have previously activated a [mod](https://wiki.luanti.org/Mod "Mod") which added some new objects, then later deactivated said mod. Now all objects from this mod will appear as an unknown objects. In this case, you can solve this simply by enabling the missing mod again. If you forgot from which mod this object originated from, point it to learn its entity ID. The part before the colum is the mod name.

Another possible cause is a bug in mods or games. Developers of a game may have made a mistake or they removed object types intentionally without any replacement. Complain to the game authors if this happens, as this is generally considered poor development practice. If unknown objects occour without you using any mods, this is almost certainly a bug.

See also
--------

*   [Unknown Item](https://wiki.luanti.org/Unknown_Item "Unknown Item")
*   [Unknown Node](https://wiki.luanti.org/Unknown_Node "Unknown Node")