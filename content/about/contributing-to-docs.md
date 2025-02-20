---
title: Contributing to Docs
aliases:
- /about-this-site/guidelines
- /about/guidelines
- /about-this-site/local-development
- /about/local-development
---

# Contributing to Docs

Luanti Documentation is written in Markdown and transformed into HTML by [Hugo](https://gohugo.io), a free and open-source static site generator. The source code is currently hosted on GitHub and deployed with GitHub Actions.

## Local Development

When cloning the repository you need to clone it recursively so that the theme submodule gets included:

```bash
git clone --recursive https://github.com/luanti-org/dev.luanti.org
```

If you have already cloned, you can fetch the submodules as such:

```bash
git submodule init
git submodule update --remote
```

This project uses [Hugo](https://gohugo.io/) to build the site and various Node packages to test it.

You can install Hugo locally as a [Node.js](https://nodejs.org) package for convenience. Node is also used for further testing scripts, like spell-checking and a11y. These scripts are described in [`package.json`](https://github.com/luanti-org/dev.luanti.org/blob/master/package.json) and [`readme.md`](https://github.com/luanti-org/dev.luanti.org/blob/master/README.md).

To install and run via Node:

```bash
npm install # Installs packages needed to build and test the site
npm start # Builds and serves the site on a localhost port for manual testing
```

If you prefer, you can manually install the relevant "extended" Hugo release from [Installation | Hugo](https://gohugo.io/installation/). Be sure to match the version present in `hugo.yaml`.

To run Hugo directly:

```bash
hugo server # This is the command internal to `npm start`
```

### Spell-checker

You can run the spell-checker using `npm run test:spelling`. You can also install the recommended "Code Spell Checker" VS Code extension to get inline annotations of apparent spelling mistakes.

If you find a word that's spelled correctly but not recognized by the spell-checker, use the context menu's "Spelling > Add Words to CSpell Configuration" command or manually update `cspell.json` to include the word.

You can disable the spell-checker with Hugo comments:

{{% comment %}} Note to readers of the source: exclude the `/*` and `*/` to unescape the shortcode. {{% /comment %}}
{{% comment %}} cspell:disable {{% /comment %}}
{{% comment %}} cspell:enable {{% /comment %}}

```md
This text is spell-checked.

{{%/* comment */%}} cspell:disable {{%/* /comment */%}}

The text is not splel-checked ;)

{{%/* comment */%}} cspell:enable {{%/* /comment */%}}

Finally, this text is spell-checked again.
```

## Guidelines

### Add [Front Matter](https://gohugo.io/content-management/front-matter/)

Front matter is metadata at the top of every file, inside a block that starts and ends with three dashes.

```yaml
---
title: Your Page Title
aliases:
- /old/page/path
---
```

Front matter should be in YAML.

The `Title` attribute is required on every markdown file, and in the case of directory `_index.md` file, the `bookCollapseSection` attribute should be set to true.

If you have moved the Markdown file from another location, add an [`aliases`](https://gohugo.io/content-management/urls/#aliases) value for redirects to keep the old URL working.

### Formats

* Use American English spelling
* Write content in Markdown
* Use webp images instead of jpg, png, or others
* Add a [language](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/creating-and-highlighting-code-blocks#syntax-highlighting) to code blocks