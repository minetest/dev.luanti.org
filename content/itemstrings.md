---
title: Itemstrings
aliases:
- /Itemstrings
---

# Itemstrings


**Itemstrings** are the internal names for items, blocks, nodes (everything which can be stored in an [inventory](/inventory)).

Syntax
------

An usual itemstring consists of a the name of the [mod](/mods) where the item originates from followed by a “:” followed by an item name. All itemstrings are case sensitive.

```
<mod_name>:<item_name>

```


Examples:

*   `default:torch` — a torch (from mod “default”)
*   `default:dirt` — dirt (from mod “default”)
*   `farming:bread` — bread (from mod “farming”)
*   `wool:orange` — orange wool (from mod “wool”)
*   `screwdriver:screwdriver` — screwdriver (from mod “screwdriver”)

There are itemstrings which don’t follow the syntax rules, see [#Special itemstrings](#special-itemstrings).

Usages
------

Itemstrings can be used as arguments used for the `/give` and `/giveme` [commands](/server/commands).

Example: `/giveme default:torch`—give yourself a torch

Special itemstrings
-------------------

There are itemstrings which do not follow the usual syntax rules. These itemstrings are always available, regardless of the activated [mods](/mods):

*   [`air`](/nodes/#air)
*   [`ignore`](/nodes/#ignore)

See also
--------

*   [Items](/engine/items)
*   [Nodes](/nodes)
