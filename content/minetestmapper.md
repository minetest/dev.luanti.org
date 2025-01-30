---
title: minetestmapper
aliases:
- /Minetestmapper
- /Luantimapper
- /Luanti-mapper
---

# Minetestmapper

![](/images/Screenshot_minetestmapper.png)

Sample minetestmapper output

The **minetestmapper** creates 2D maps of your [world](/worlds), where one [node](/nodes) corresponds to one pixel.

### Usage

_This describes the usage of the C++ minetestmapper. The usage of minetestmapper.py is similar._

Make sure there is a `colors.txt` in the same folder as the mapper. The default one does not support any mods. You can download VanessaE’s more complete [colors.txt](https://web.archive.org/web/20211015192853/http://daconcepts.com/vanessa/hobbies/minetest/colors.txt), containing support for hundreds of mods.

On GNU/Linux, open a terminal in the folder the mapper is. Create a map using this command:

```sh
./minetest_mapper -i /home/user/.minetest/worlds/my_world/ -o /home/user/map.png
```

Having Luanti running in place, you might have to modify the world path.
  
On Windows, **Shift + Right click** in the folder the mapper is in, then select **Open a command window here**. To create a map, type this command:

```sh
minetest_mapper.exe -i "C:\your_path_to_luanti\worlds\example\" -o map.png
```
  
The geometry option allows you to define an area to map. Use it between “./minetestmapper” and the input “-i”.

```sh
minetest_mapper.exe --geometry -10000:-10000+20000+20000 -i "C:\your_path_to_luanti\worlds\example\" -o map.png
```

Result: A 20.2 MiB file covering a 20,000 × 20,000 area starting in the lower left corner at X=-10,000; Y=-10,000

### Versions

Currently, there are three mappers. **It is recommended to use the C++ version.**

#### minetestmapper.py

A mapper written in Python. It's very slow.

#### minetestmapper in C++

The minetestmapper rewritten with C++. It is much faster. The code can be found on [GitHub](https://github.com/luanti-org/minetestmapper).

#### minetestmapper-numpy.py

An improved version of the Python mapper with many additional features, like side view, scaling and fog. It is 8 to 10 times faster than the original minetestmapper.py, but still slower than the C++ version. Information about installation and usage can be found in the [forum](https://forum.luanti.org/viewtopic.php?f=14&t=8730).
