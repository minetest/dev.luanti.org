---
title: Local Development
---

# Local Development

_(anyone)_

To build locally, you will need to first [install Hugo](https://gohugo.io/installation/).
* Note, you need the extended version

When cloning the repository you need to clone it recursively so that the theme submodule gets included:

```bash
git clone --recursive https://github.com/minetest/dev.luanti.org
```

If you have already cloned you can fetch the submodules as such:

```bash
git submodule init
git submodule update --remote
```

To launch the Hugo development server run `hugo server`. It will watch and regenerate whenever changes are made.

To generate the site once without starting the server you can simply run `hugo`.

Some additional checks are run in [Node](npmjs.org):

```bash
npm install
npm test
```

You can disable the spell checker with Hugo comments:

```md
This text is spell-checked.

{{% comment %}} cspell:disable {{% /comment %}}

The text is not splel-checked ;)

{{% comment %}} cspell:enable {{% /comment %}}

Finally, this text is spell-checked again.
```