# hast-util-phrasing

[![Build][build-badge]][build]
[![Coverage][coverage-badge]][coverage]
[![Downloads][downloads-badge]][downloads]
[![Size][size-badge]][size]
[![Sponsors][sponsors-badge]][collective]
[![Backers][backers-badge]][collective]
[![Chat][chat-badge]][chat]

[**hast**][hast] utility to check if a [*node*][node] is [*phrasing*][spec]
content.

## Install

[npm][]:

```sh
npm install hast-util-phrasing
```

## Use

```js
var phrasing = require('.')

// Given flow content:
phrasing({
  type: 'element',
  tagName: 'div',
  children: [{type: 'text', value: 'Alpha'}]
})
// => false

// Given a phrasing element:
phrasing({
  type: 'element',
  tagName: 'meta',
  properties: {itemProp: 'bravo'},
  children: []
})
// => true

// Given a non-phrasing element:
phrasing({
  type: 'element',
  tagName: 'meta',
  properties: {charSet: 'utf8'},
  children: []
})
// => false

// Given text:
phrasing({type: 'text', value: 'Delta'})
// => true
```

## API

### `phrasing(node)`

Check if the given value is [*phrasing*][spec] content.

###### Parameters

*   `node` (`*`) — Value to check, typically [`Node`][node].

###### Returns

`boolean` — Whether `node` passes the test.

## Security

`hast-util-phrasing` does not change the syntax tree so there are no openings
for [cross-site scripting (XSS)][xss] attacks.

## Related

*   [`hast-util-is-element`](https://github.com/syntax-tree/hast-util-is-element)
    — check if a node is a (certain) element
*   [`hast-util-has-property`](https://github.com/syntax-tree/hast-util-has-property)
    — check if a node has a property
*   [`hast-util-is-body-ok-link`](https://github.com/rehypejs/rehype-minify/tree/master/packages/hast-util-is-body-ok-link)
    — check if a node is “Body OK” link element
*   [`hast-util-is-conditional-comment`](https://github.com/rehypejs/rehype-minify/tree/master/packages/hast-util-is-conditional-comment)
    — check if a node is a conditional comment
*   [`hast-util-is-css-link`](https://github.com/rehypejs/rehype-minify/tree/master/packages/hast-util-is-css-link)
    — check if a node is a CSS link element
*   [`hast-util-is-css-style`](https://github.com/rehypejs/rehype-minify/tree/master/packages/hast-util-is-css-style)
    — check if a node is a CSS style element
*   [`hast-util-embedded`](https://github.com/syntax-tree/hast-util-embedded)
    — check if a node is an embedded element
*   [`hast-util-heading`](https://github.com/syntax-tree/hast-util-heading)
    — check if a node is a heading element
*   [`hast-util-interactive`](https://github.com/syntax-tree/hast-util-interactive)
    — check if a node is interactive
*   [`hast-util-is-javascript`](https://github.com/rehypejs/rehype-minify/tree/master/packages/hast-util-is-javascript)
    — check if a node is a JavaScript script element
*   [`hast-util-labelable`](https://github.com/syntax-tree/hast-util-labelable)
    — check whether a node is labelable
*   [`hast-util-script-supporting`](https://github.com/syntax-tree/hast-util-script-supporting)
    — check if a node is a script-supporting element
*   [`hast-util-sectioning`](https://github.com/syntax-tree/hast-util-sectioning)
    — check if a node is a sectioning element
*   [`hast-util-transparent`](https://github.com/syntax-tree/hast-util-transparent)
    — check if a node is a transparent element
*   [`hast-util-whitespace`](https://github.com/syntax-tree/hast-util-whitespace)
    — check if a node is inter-element whitespace

## Contribute

See [`contributing.md` in `syntax-tree/.github`][contributing] for ways to get
started.
See [`support.md`][support] for ways to get help.

This project has a [code of conduct][coc].
By interacting with this repository, organization, or community you agree to
abide by its terms.

## License

[MIT][license] © [Titus Wormer][author]

<!-- Definitions -->

[build-badge]: https://img.shields.io/travis/syntax-tree/hast-util-phrasing.svg

[build]: https://travis-ci.org/syntax-tree/hast-util-phrasing

[coverage-badge]: https://img.shields.io/codecov/c/github/syntax-tree/hast-util-phrasing.svg

[coverage]: https://codecov.io/github/syntax-tree/hast-util-phrasing

[downloads-badge]: https://img.shields.io/npm/dm/hast-util-phrasing.svg

[downloads]: https://www.npmjs.com/package/hast-util-phrasing

[size-badge]: https://img.shields.io/bundlephobia/minzip/hast-util-phrasing.svg

[size]: https://bundlephobia.com/result?p=hast-util-phrasing

[sponsors-badge]: https://opencollective.com/unified/sponsors/badge.svg

[backers-badge]: https://opencollective.com/unified/backers/badge.svg

[collective]: https://opencollective.com/unified

[chat-badge]: https://img.shields.io/badge/chat-spectrum-7b16ff.svg

[chat]: https://spectrum.chat/unified/syntax-tree

[npm]: https://docs.npmjs.com/cli/install

[license]: license

[author]: https://wooorm.com

[contributing]: https://github.com/syntax-tree/.github/blob/master/contributing.md

[support]: https://github.com/syntax-tree/.github/blob/master/support.md

[coc]: https://github.com/syntax-tree/.github/blob/master/code-of-conduct.md

[spec]: https://html.spec.whatwg.org/#phrasing-content-2

[hast]: https://github.com/syntax-tree/hast

[node]: https://github.com/syntax-tree/hast#nodes

[xss]: https://en.wikipedia.org/wiki/Cross-site_scripting
