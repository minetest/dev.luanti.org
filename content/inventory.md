---
title: Inventory
aliases:
- /Inventory
- /Inventory_menu
---

# Inventory

An **inventory** is primarily used to store [item stacks](/items#item-stack). There are other uses, such as crafting. An inventory consists of a rectangular grid of item slots. Each item slot can be either empty or hold one item stack. Item stacks can be moved freely between slot and slot, given that the destination slot is either empty or of the same item type.

Inventory menu
--------------

The **inventory menu** is a special in-game menu where the player normally, but not necessarily, finds an inventory and other related stuff.

### Notable examples

![](/images/inventory/Inventory_menu_illustrated.png)

Illustration of the default inventory menu in [Minetest Game](https://content.luanti.org/packages/Minetest/minetest_game/).

The default inventory menu consists of a 3 × 3 crafting grid with an output slot at the upper part and an 8 × 4 inventory (which is also referred to as the “player inventory”) at the lower part. The first line of the player inventory make the hotbar.

The default inventory menu is used in games that do not specify a different inventory menu.

![](/images/inventory/Creative_inventory_menu.png)

Illustration of the creative inventory menu in Minetest Game, using the [sfinv mod](https://content.luanti.org/packages/rubenwardy/sfinv/).

The creative inventory menu is a variant of the default inventory menu and is used when creative mode is turned on. It adds a creative inventory and a trash slot.

The creative inventory is an unchangeable take-only inventory with almost all available items. Since there are many _available_ items, the creative inventory is organized in several pages which can be flipped using the buttons **<<** and **>>**.

The trash slot destroys any item stack which is placed into it immediately. It is useful to get rid of unwanted items.

### In other games

The inventory menu can be completely customized. [Mods](/mods) may add inventories and basically add every other available menu widget the modders would like to. Mods can change the design of the menu and much more. In fact the inventory menu is really just a menu. The inventory menu can be designed to contain much more than just inventories or it can be designed to contain no inventories at all.

Controls
--------

In the default configuration, the inventory menu can be opened and closed with I. If the game defines an empty inventory then this keybind will not work.

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
*   Hold down Shift+click while moving mouse over item slots: Continuously **move item stacks** to other inventory (if available)
*   Double click: **Pick up all item stacks of the same type** in the inventory
*   Pick up an item stack with leftclick, keep the mouse button pressed and drag cursor over slots: **Pick up items** of the same type
*   Shift+click on crafting output slot: **Craft and move** result to inventory
    *   Left mouse button: **Craft as many as possible**
    *   Mouse wheel: **Craft 10 times**
    *   Right mouse button: **Craft once**

When you're **holding an item stack on your cursor**:

*   Drag cursor over slots while left-clicking: **Split stacks evenly** over the slots you touched
*   Drag cursor over slots while middle-clicking: **Place 10 items** on every slot you touched
*   Drag cursor over slots while right-clicking: **Place 1 item** on every slot you touched

### Inventory debug

This is something for developers and only works if you have the “debug” [privilege](/privileges). If you press F5 when the inventory menu is open, you activate the inventory debug. The formspec elements that your cursor hovers will be highlighted. Press F5 again to disable inventory debug.

Inventories in Minetest Game
----------------------------

### Player inventory

![](/images/inventory/Inventory.png)

The player inventory in Minetest Game

The default player inventory has a size of 8 rows and 4 lines, providing 32 item slots of storage. It is always available. The top line makes the hotbar.

### Other inventories

Other inventories are the crafting grid and in the furnace. The crafting grid has the same properties of an inventory but you can also craft new items with it. You keep your items if you store them in the crafting grid and close the inventory menu. Even the fuel and smelting slots of the furnace are in fact just special cases of inventories which are, in this case, 1×1 inventories, even though the latter is limited to “fuel”-type items.

For the purpose of this wiki, an ordinary inventory in the inventory menu is referred to as “player inventory”.
