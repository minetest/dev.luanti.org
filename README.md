# Luanti Documentation

Hosted by GitHub Pages, generated with [Hugo](https://gohugo.io/).

Theme: [hugo-book](https://themes.gohugo.io/themes/hugo-book/)

See [/content](/content/) for content.

See [About](content/about/_index.md) for more information

## package.json

`package.json` dependencies and scripts are described here for readability:

- scripts
  - `build`: Builds the site to ensure changes are valid
  - `build:ci`: Builds the site but fails if any warnings are detected. Used in our CI pipeline.
  - `format:fix`: Fixes formatting of the `package.json` file
  - `start`: Builds and serves the site at http://localhost:1313 with Hugo.
  - `test:a11y`: Builds and serves the site, then uses Playwright and axe to test accessibility
  - `test:a11y:tests`: Not meant for independent use, only as part of `test:a11y`
  - `test:links`: Tests validity of all links in the site. WIP, ref [#177](https://github.com/luanti-org/dev.luanti.org/issues/177)
  - `test:spelling`: Reports all apparent spelling errors. WIP, ref [#83](https://github.com/luanti-org/dev.luanti.org/issues/83) for details.
- dependencies
  - `hugo-extended`: Static site generator that turns Markdown and shortcodes into HTML
- devDependencies
  - [`@axe-core/playwright`](https://npmjs.com/package/@axe-core/playwright): A11y tester bindings for Playwright
  - [`@playwright/test`](https://npmjs.com/package/@playwright/test): Browser automation and test library
  - [`cspell`](https://npmjs.com/package/cspell): Spellchecker
  - [`sort-package-json`](https://npmjs.com/package/sort-package-json): Sorts package.json files for consistency
  - [`start-server-and-test`](https://npmjs.com/package/start-server-and-test): Allows easy setup and teardown of complex tests, like our a11y tests
