# Inventory - Luanti Wiki


An **inventory** is primarily used to store [item stacks](https://wiki.luanti.org/Item_stack "Item stack"). There are other uses, such as [crafting](https://wiki.luanti.org/Crafting "Crafting"). An inventory consists of a rectangular grid of item slots. Each item slot can be either empty or hold one item stack. Item stacks can be moved freely between slot and slot, given that the destination slot is either empty or of the same item type.

Controls
--------

You only use the mouse to take, drop and exchange items to move item stacks around.

### Taking

You can **take** items from an occupied slot if the cursor holds nothing.

*   Left click: take entire item stack
*   Right click: take half from the item stack (rounding up if uneven)
*   Middle click: take 10 items from the item stack
*   Roll mouse wheel down: take 1 item from the item stack

### Dropping

You can **drop** items onto a slot if the cursor holds 1 or more items and the slot is either empty or contains an item stack of the same item type.

*   Left click: drop entire item stack
*   Right click or roll mouse wheel up: drop 1 item of the item stack
*   Middle click: drop 10 items of the item stack

### Exchanging

You can **exchange** items if the cursor holds 1 or more items and the destination slot is occupied by a different item type.

*   Left, middle and right click: exchange item stacks from cursor and from selected item slot

### Throwing away

If you hold an item stack and click with it somewhere outside the menu, the item stack gets thrown away into the environment.

### Shortcuts

The inventory has many shortcuts for convenience. Using the mouse and the shift key, you can speed up many tasks. For example, if you hold down Shift while clicking on an item in the inventory, it will be moved to another relevant inventory (if available), like from the player inventory to the chest inventory or vice-versa.

When you're **holding no item stack on your cursor**:

*   Shift+click: **Move item stack** to other inventory (if available)
*   Hold down Shift+click while moving mouse over item slots: Continously **move item stacks** to other inventory (if available)
*   Double click: **Pick up all itemstacks of the same type** in the inventory
*   Pick up an item stack with leftclick, keep the mouse button pressed and drag cursor over slots: **Pick up items** of the same type
*   Shift+click on crafting output slot: **[Craft](https://wiki.luanti.org/Crafting "Crafting") and move** result to inventory
    *   Left mouse button: **Craft as many as possible**
    *   Mouse wheel: **Craft 10 times**
    *   Right mouse button: **Craft once**

When you're **holding an item stack on your cursor**:

*   Drag cursor over slots while leftclicking: **Split stacks evenly** over the slots you touched
*   Drag cursor over slots while middleclicking: **Place 10 items** on every slot you touched
*   Drag cursor over slots while rightclicking: **Place 1 item** on every slot you touched

### Inventory debug

This is something for developers and only works if you have the “debug” [privilege](https://wiki.luanti.org/Privileges "Privileges"). If you press F5 when the inventory menu is open, you activate the inventory debug. The formspec elements that your cursor hovers will be highlighted. Press F5 again to disable inventory debug.

Inventories in [Minetest Game](https://wiki.luanti.org/Games/Minetest_Game "Games/Minetest Game")
-------------------------------------------------------------------------------------------------

### Player inventory

[![](https://wiki.luanti.org/images/thumb/d/db/Inventory.png/250px-Inventory.png)](https://wiki.luanti.org/File:Inventory.png)

The player inventory is in the [inventory menu](https://wiki.luanti.org/Inventory_menu "Inventory menu") and has a size of 8 rows and 4 lines, providing 32 item slots of storage. It is always available. The top line makes the [hotbar](https://wiki.luanti.org/Hotbar "Hotbar").

### [Chest](https://wiki.luanti.org/Chest "Chest") and [Locked Chest](https://wiki.luanti.org/Locked_Chest "Locked Chest")

Chests and locked chests both provide 8 × 4 inventories.

### [Bookshelf](https://wiki.luanti.org/Bookshelf "Bookshelf")

A bookshelf has a special 8×2 inventory which can only be used for 1 [book](https://wiki.luanti.org/Book "Book") per slot.

### [Vessels Shelf](https://wiki.luanti.org/Vessels_Shelf "Vessels Shelf")

A vessels shelf has a special 8×2 inventory which can only be used for glass bottles and drinking glasses.

### [Bones](https://wiki.luanti.org/Bones "Bones")

When a [player](https://wiki.luanti.org/Player "Player") dies, a bones block is generated. It has an inventory which contains all the items of the player who died. The bones’ inventory acts in many special ways, see [Bones](https://wiki.luanti.org/Bones "Bones") for more information.

### Other inventories

Other inventories are the [crafting grid](https://wiki.luanti.org/Crafting#Crafting_grid_and_output_slot "Crafting") and in the [furnace](https://wiki.luanti.org/Furnace "Furnace"). The crafting grid has the same properties of an inventory but you can also [craft](https://wiki.luanti.org/Crafting "Crafting") new items with it. You keep your items if you store them in the crafting grid and close the inventory menu. Even the fuel and smelting slots of the furnace are in fact just special cases of inventories which are, in this case, 1×1 inventories, even though the latter is limited to “fuel”-type items.

Inventories in other [games](https://wiki.luanti.org/Games "Games")
-------------------------------------------------------------------

Other [mods](https://wiki.luanti.org/Mods "Mods") or games can completely customize the inventory menu to change the inventories there and also add inventories basicly whereever the modder wants to. In fact, Minetest Game just shows one possibility to use inventories.

For the purpose of this wiki, an ordinary inventory in the inventory menu is refered to as “player inventory”.
