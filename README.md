# remark-preset-prettier

[![GitHub Actions](https://github.com/JounQin/remark-preset-prettier/workflows/CI/badge.svg)](https://github.com/JounQin/remark-preset-prettier/actions/workflows/ci.yml)
[![Codacy Grade](https://img.shields.io/codacy/grade/d2f82a40047a4b69bcfc2e8afc73ea83)](https://www.codacy.com/app/JounQin/remark-preset-prettier)
[![type-coverage](https://img.shields.io/badge/dynamic/json.svg?label=type-coverage&prefix=%E2%89%A5&suffix=%&query=$.typeCoverage.atLeast&uri=https%3A%2F%2Fraw.githubusercontent.com%2FJounQin%2Fremark-preset-prettier%2Fmaster%2Fpackage.json)](https://github.com/plantain-00/type-coverage)
[![npm](https://img.shields.io/npm/v/remark-preset-prettier.svg)](https://www.npmjs.com/package/remark-preset-prettier)
[![GitHub release](https://img.shields.io/github/release/JounQin/remark-preset-prettier)](https://github.com/JounQin/remark-preset-prettier/releases)

[![David Peer](https://img.shields.io/david/peer/JounQin/remark-preset-prettier.svg)](https://david-dm.org/JounQin/remark-preset-prettier?type=peer)
[![David](https://img.shields.io/david/JounQin/remark-preset-prettier.svg)](https://david-dm.org/JounQin/remark-preset-prettier)
[![David Dev](https://img.shields.io/david/dev/JounQin/remark-preset-prettier.svg)](https://david-dm.org/JounQin/remark-preset-prettier?type=dev)

[![Conventional Commits](https://img.shields.io/badge/conventional%20commits-1.0.0-yellow.svg)](https://conventionalcommits.org)
[![JavaScript Style Guide](https://img.shields.io/badge/code_style-standard-brightgreen.svg)](https://standardjs.com)
[![Code Style: Prettier](https://img.shields.io/badge/code_style-prettier-ff69b4.svg)](https://github.com/prettier/prettier)

> Turns off all rules that are unnecessary or might conflict with [Prettier][].

## TOC <!-- omit in toc -->

- [Disabled remark-lint plugins](#disabled-remark-lint-plugins)
- [Install](#install)
- [Usage](#usage)
  - [Via config like `.remarkrc`](#via-config-like-remarkrc)
  - [Via ESLint(recommended)](#via-eslintrecommended)
  - [Via remark-cli](#via-remark-cli)
  - [Via Node API](#via-node-api)
- [remark-retext issue](#remark-retext-issue)
- [Changelog](#changelog)
- [License](#license)

## Disabled remark-lint plugins

1. [blank-lines-1-0-2](https://www.npmjs.com/package/remark-lint-blank-lines-1-0-2)
2. [blockquote-indentation](https://www.npmjs.com/package/remark-lint-blockquote-indentation)
3. [books-links](https://www.npmjs.com/package/remark-lint-books-links)
4. [checkbox-character-style](https://www.npmjs.com/package/remark-lint-checkbox-character-style)
5. [code-block-style](https://www.npmjs.com/package/remark-lint-code-block-style)
6. [definition-case](https://www.npmjs.com/package/remark-lint-definition-case)
7. [definition-spacing](https://www.npmjs.com/package/remark-lint-definition-spacing)
8. [emphasis-marker](https://www.npmjs.com/package/remark-lint-emphasis-marker)
9. [fenced-code-marker](https://www.npmjs.com/package/remark-lint-fenced-code-marker)
10. [final-newline](https://www.npmjs.com/package/remark-lint-final-newline)
11. [hard-break-spaces](https://www.npmjs.com/package/remark-lint-hard-break-spaces)
12. [heading-style](https://www.npmjs.com/package/remark-lint-heading-style)
13. [heading-whitespace](https://www.npmjs.com/package/remark-lint-heading-whitespace)
14. [link-title-style](https://www.npmjs.com/package/remark-lint-link-title-style)
15. [list-item-bullet-indent](https://www.npmjs.com/package/remark-lint-list-item-bullet-indent)
16. [list-item-content-indent](https://www.npmjs.com/package/remark-lint-list-item-content-indent)
17. [list-item-indent](https://www.npmjs.com/package/remark-lint-list-item-indent)
18. [list-item-spacing](https://www.npmjs.com/package/remark-lint-list-item-spacing)
19. [maximum-line-length](https://www.npmjs.com/package/remark-lint-maximum-line-length)
20. [no-blockquote-without-marker](https://www.npmjs.com/package/remark-lint-no-blockquote-without-marker)
21. [no-consecutive-blank-lines](https://www.npmjs.com/package/remark-lint-no-consecutive-blank-lines)
22. [no-heading-content-indent](https://www.npmjs.com/package/remark-lint-no-heading-content-indent)
23. [no-inline-padding](https://www.npmjs.com/package/remark-lint-no-inline-padding)
24. [no-long-code](https://www.npmjs.com/package/remark-lint-no-long-code)
25. [no-table-indentation](https://www.npmjs.com/package/remark-lint-no-table-indentation)
26. [ordered-list-marker-style](https://www.npmjs.com/package/remark-lint-ordered-list-marker-style)
27. [ordered-list-marker-value](https://www.npmjs.com/package/remark-lint-ordered-list-marker-value)
28. [rule-style](https://www.npmjs.com/package/remark-lint-rule-style)
29. [spaces-around-number](https://www.npmjs.com/package/remark-lint-spaces-around-number)
30. [spaces-around-word](https://www.npmjs.com/package/remark-lint-spaces-around-word)
31. [strong-marker](https://www.npmjs.com/package/remark-lint-strong-marker)
32. [table-cell-padding](https://www.npmjs.com/package/remark-lint-table-cell-padding)
33. [table-pipe-alignment](https://www.npmjs.com/package/remark-lint-table-pipe-alignment)
34. [table-pipes](https://www.npmjs.com/package/remark-lint-table-pipes)
35. [unordered-list-marker-style](https://www.npmjs.com/package/remark-lint-unordered-list-marker-style)

## Install

```sh
# yarn
yarn add -D remark-preset-prettier

# npm
npm i -D remark-preset-prettier
```

## Usage

### Via [config](https://github.com/remarkjs/remark/tree/master/packages/remark-cli) like `.remarkrc`

```json
{
  "plugins": [
    "preset-lint-consistent",
    "preset-lint-markdown-style-guide",
    "preset-lint-recommended",
    "preset-prettier"
  ]
}
```

### Via ESLint(recommended)

Please use _[eslint-plugin-mdx][]_ which works perfectly with [ESLint][] and [Remark][] both together.

```jsonc
{
  "extends": "plugin:mdx/recommended"
}
```

### Via remark-cli

```sh
remark . --use preset-lint-consistent preset-lint-markdown-style-guide preset-lint-recommended preset-prettier
```

### Via Node API

```js
const report = require('vfile-reporter')
const remark = require('remark')
const consistent = require('remark-preset-lint-consistent')
const styleGuide = require('remark-preset-lint-markdown-style-guide')
const recommended = require('remark-preset-lint-recommended')
const prettier = require('remark-preset-lint-prettier')

const file = remark()
  .use(consistent)
  .use(styleGuide)
  .use(recommended)
  .use(prettier)
  .processSync('_Hello world_')

console.log(report(file))
```

## [remark-retext][] issue

[retext-sentence-spacing][] is a plugin of [retext][], and [remark-retext][] makes it possible to use [retext][] plugins together with [remark][], and [retext-sentence-spacing][] may conflict with [Prettier][].

However, [remark-retext][] can only be enabled once what means we can not simply disable rule [retext-sentence-spacing][] in this preset which is actually meaningless.

If you do have problems between [retext-sentence-spacing][] and [Prettier][], you have to override the whole configuration of [remark-retext][] like following:

```js
// .remarkrc.js
const wooorm = require('retext-preset-wooorm')

module.exports = {
  plugins: [
    'preset-wooorm', // other preset(s) or plugin(s)
    'preset-prettier',
    [
      'retext',
      unified()
        .use(wooorm) // retext preset(s)
        .use({
          plugins: [[require('retext-sentence-spacing'), false]],
        }),
    ],
  ],
}
```

## Changelog

Detailed changes for each release are documented in [CHANGELOG.md](./CHANGELOG.md).

## License

[MIT][] © [JounQin][]@[1stG.me][]

[1stg.me]: https://www.1stg.me
[eslint]: https://eslint.org
[eslint-plugin-mdx]: https://github.com/rx-ts/eslint-mdx
[jounqin]: https://GitHub.com/JounQin
[mit]: http://opensource.org/licenses/MIT
[prettier]: https://prettier.io
[remark]: https://github.com/remarkjs/remark
[remark-retext]: https://github.com/remarkjs/remark-retext
[retext]: https://github.com/retextjs/retext
[retext-sentence-spacing]: https://github.com/retextjs/retext-sentence-spacing
