---
Title: Guidelines
---

# Guidelines

## Every page should have [Front Matter](https://gohugo.io/content-management/front-matter/)

Front Matter is metadata at the top of every file, inside a block that starts and ends with three dashes.

```md
---
Title: PAGE TITLE
---
```

Front matter can be in (at the time of writing) yaml, toml, and json. We currently define it in yaml format.

### Required attributes

The `Title` attribute is required on every markdown file, and in the case of directory `_index.md` file, the `bookCollapseSection` attribute should be set to true.

### Optional attributes

if you have moved the markdown file from another location, add the [`alias`](https://gohugo.io/content-management/urls/#aliases) attribute for redirects to keep the old url working.

## Formats

* Content must be in markdown
* webp images are encouraged, but not currently required
* Code blocks should have a [language](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/creating-and-highlighting-code-blocks#syntax-highlighting) for syntax highlighting