---
title: Items
alias:
- /Items
---

# Items

## Unknown Item

![](/images/Unknown_Item.png)

Inventory image of an unknown item.


An **unknown item** is a pseudo-item in Luanti to represent an item of which the item definition is unknown. These items should never appear in the game, and it's always an error when you encounter it.

Behaviour
---------

Most types of world interactions are not possible. Dropping an unknown item is not possible. You can still store and move this item in inventories.

If you try to place, use or drop an unknown item, an error message will be shown to the server. This message is not visible if you are connected to a server as a normal player. The error message reveals the item's [itemstring](/itemstrings).

Internally, an unknown item still knows the “real” item it represents and the associated data. To fix problems with unknown items, check the troubleshooting section below. You can destroy unknown items with the `pulverize` [server command](/server-commands).

Troubleshooting
---------------

A common reason for this item to appear is when you have previously activated a [mod](/mods) which added some new item, stored some of these items in an inventory, then later deactivated said mod. Now all items from this mod will appear as an unknown items. In this case, you can solve this simply by enabling the missing mod again. If you forgot to which mod this item belonged, rightclick with the item in hand to see its itemstring. The part before the column is the mod name.

Another source of this item is a bug in mods or games or just general developer clumsiness. Developers of a game may have made a mistake or removed items intentionally without any replacement. Complain to the game authors if this happens, as this is generally considered poor development practice. If unknown items occur without you using any mods, this is almost certainly a bug.

Technical background
--------------------

Technically, an unknown item still kinda acts like a normal item, and most item query and manipulation functions will still work. If you query the itemstring of an unknown item with e.g. `itemstack:get_name()`, you get the itemstring which the unknown item represents. To find out in Lua whether an item stack is unknown, call `itemstack:is_known()`.

See also
--------

*   [Unknown Node](/nodes#unknown-node)
*   [Unknown Object](/objects#unknown-object)
