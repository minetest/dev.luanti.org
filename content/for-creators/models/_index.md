---
title: Models
aliases:
- /models
bookCollapseSection: true
---

# Models

Luanti supports a few different model formats.

### `.obj` Format

Useful for static models, doesn't not support animation.

### `.b3d` Format

Originally from the Blitz3D Engine, this format is widespread due to its animation support. You will need [this](https://github.com/GreenXenith/io_scene_b3d) extension to export models from blender. It is recommended that you keep the source .blend file due to importing not being supported in the extension. Using gltf/glb is preferred if you don't mind not supporting older 5.x releases.

### `.x` Format

Alternative to b3d that supports animations. Unless you have a specific reason, should use gltf/glb or b3d.

### `.gltf / .glb` Format

Modern animation model support, added in release 5.10. Using this format means you can't (easily) support versions before 5.10. See https://forum.luanti.org/viewtopic.php?t=31133 regarding exporting from blender at this time.

### Node Boxes Format

{{< notice note >}}
This Format is only supported for nodes.
{{< /notice >}}

See https://api.luanti.org/nodes/#node-boxes.

## Editors

* [BlockBench](/for-creators/models/blockbench)
* [Blender](/for-creators/models/using-blender)
