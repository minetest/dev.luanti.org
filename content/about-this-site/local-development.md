---
title: Local Development
---

# Local Development

_(anyone)_

When cloning the repository you need to clone it recursively so that the theme submodule gets included:

```bash
git clone --recursive https://github.com/minetest/dev.luanti.org
```

If you have already cloned you can fetch the submodules as such:

```bash
git submodule init
git submodule update --remote
```

To build locally, you will need to first [install Node](https://nodejs.org).

```bash
npm install # Installs packages needed to build and test the site
npm start # Builds and serves the site on a localhost port for manual testing
```

Further scripts are described in `package.json` and `readme.md`.

## Spellchecker

You can disable the spell checker with Hugo comments:

```md
This text is spell-checked.

{{% comment %}} cspell:disable {{% /comment %}}

The text is not splel-checked ;)

{{% comment %}} cspell:enable {{% /comment %}}

Finally, this text is spell-checked again.
```