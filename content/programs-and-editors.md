---
title: Programs and Editors
aliases:
- /Programs_and_Editors
---

# Programs and Editors

This is a list of unofficial [Luanti](/Luanti)-related software.

This is not a comprehensive list, for more see [Luanti-related projects](https://forum.minetest.net/viewforum.php?f=14) in the forum.

Mapping
-------

Name | Description | Info/webpage | Author
--|--|--|--
Minetest Mapper | Creates 2D map images of an already existing world. One block corresponds to one pixel. There is also a Minetest Mapper GUI available. | [minetestmapper](/minetestmapper) | Many contributors
Amidst for Minetest | Creates a map of biomes without actually creating the world. This tool just needs a world type, biome profile and seed. Can also view the biomes as Voronoi diagrams. | forum | Dr. Frankenstone
MTSatellite | A real-time Web mapping system. Play on your world and share a map of it in the Web, live. | forum | s-l-teichmann
Minetest mapserver | A real-time Web mapping system with POI, player, shop and item-search support. Play on your world and share a map of it in the Web, live. written in Go. | forum | BuckarooBanzay
Onomatopoeia | Creates isometric images of already existing worlds. | forum | Zeg9 and HybridDog

World editing
-------------


Name | Description | Info/webpage | Author
--|--|--|--
Geo mapgen | Generate worlds from real-world topographical data. Reads GeoTiff land cover data and digital elevation models such as those provided by SRTM | forum | Gael de Sailly
Real Terrain | Use image files as heightmaps and biome-maps to generate worlds. | forum | bobomb
mtmapprune | Prunes the map.sqlite file of a world and deletes blocks outside a specified range. | forum | sofar
WorldPainter | WorldPainter is a Minecraft tool that provides Luanti support via a plugin. WorldPainter generates the world according to your instructions about the terrain height and type, and any additional "layers" you've painted which can add things like trees and other vegetation, caves or any type of custom object. You can paint and sculpt the terrain by hand, but you can also use height maps and/or image masks. | forum | Captain Chaos
MapEditr | MapEditr is a command-line tool for fast manipulation of Luanti map database files. Functionally similar to WorldEdit, but runs outside of the game and is designed for handling larger tasks. | forum | Random Geek
MapEdit | Superseded by MapEditr (above) | forum | Random Geek

Convert data from _Minecraft_
-----------------------------


Name | Description | Info/webpage | Author
--|--|--|--
mcimport | A world converter for whole Minecraft maps (savegames), outputting a new, playable Luanti world. For GNU/Linux. | forum | many contributors
mcresconvert | Convert Minecraft resource packs and texture packs to Luanti texture packs | forum | many contributors

Twoelk also describes [other converters for importing Minecraft data into Luanti](https://forum.minetest.net/viewtopic.php?p=251194&sid=8558c08027ecfd8d6f08620c9344882f#p251194).

Servers
-------

Name | Description | Info/webpage | Author
--|--|--|--
mtmediasrv | Minetest Remote Media Server: Distribute Luanti media (textures, models, sounds) to Luanti clients for multiplayer server owners that wish to have their media hosted on a remote media server URL. | forum | sofar

Development
-----------

See [Development Tools](/development-tools)
