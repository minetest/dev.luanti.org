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

This project uses [Hugo](https://gohugo.io/) to build the site and various Node packages to test it.

You can install Hugo locally as a [Node.js](https://nodejs.org) package for convenience. Node is also used for further testing scripts, like spell-checking and a11y. These scripts are described in `package.json` and `readme.md`.

To install and run via Node:

```bash
npm install # Installs packages needed to build and test the site
npm start # Builds and serves the site on a localhost port for manual testing
```

If you prefer, you can manually install the relevant "extended" release globally from [Installation | Hugo](https://gohugo.io/installation/). Be sure to match the version present in `hugo.yaml`.

To run globally:

```bash
hugo server # This is the command internal to the `npm start` command
```

## Spellchecker

You can disable the spell checker with Hugo comments:

```md
This text is spell-checked.

{{% comment %}} cspell:disable {{% /comment %}}

The text is not splel-checked ;)

{{% comment %}} cspell:enable {{% /comment %}}

Finally, this text is spell-checked again.
```