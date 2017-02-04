[![Published on webcomponents.org](https://img.shields.io/badge/webcomponents.org-published-blue.svg)](https://www.webcomponents.org/element/arsnebula/nebula-sidebar-layout)

[![Build Status](https://saucelabs.com/browser-matrix/arsnebula.svg)](https://saucelabs.com/beta/builds/47e7f0769191423eafd4f9182aa465d7)

# \<nebula-sidebar-layout\>

A web component to display a collapsable sidebar layout.

* Two-column application layout using slots
* Fixed sidebar container on the left, fluid content container on the right
* Sidebar collapses to a drawer menu at a configurable breakpoint
* Automatically makes the content container `inert` when the drawer is open
* Easily customized using CSS custom variables, mixins or style properties

> Warning: This element utilizes features of [ECMAScript 2015](http://www.ecma-international.org/ecma-262/6.0/) which may not be supported by all browsers. To ensure support by all browsers, consider using the [Core-js Polyfill](https://github.com/zloirock/core-js).

> Warning: This element utilizes [Inert Subtrees](https://html.spec.whatwg.org/multipage/interaction.html#inert-subtrees), a draft feature of HTML which may not be supported by all browsers. To ensure support by all browsers, consider using the [Inert Polyfill](https://github.com/GoogleChrome/inert-polyfill).

## Installation

```
$ bower install -S arsnebula/nebula-sidebar-layout
```

## Usage

Import the element:

```
<link rel="import" href="/bower_components/nebula-sidebar-layout/nebula-sidebar-layout.html"> 
```

Add and configure the element markup. The element utilizes offscreen positioning for the drawer when collapsed, so the the `body` and and other parent elements should be set to fill the browser screen.

The following is a sample stylesheet for ensuring the body matches the viewport.

```css
<head>
  <style>
    html, body {
      position: relative;
      border: 0;
      margin: 0;
      padding: 0;
      min-height: 100vh;
      width: 100%;
      height: 100%;
      overflow: hidden;
      overflow-y: auto;
      box-sizing: border-box;
    }
  </style>
</head>
```

Add the element markup. By default, the `sidebar` and `content` slots are vertical flexbox containers that will fill the viewport. Style attributes like `width` and `backdrop-color` can be used in markup, or style the element with CSS variables.

```html
<nebula-sidebar-layout
  id="sidebar"
  width="280px"
  breakpoint="(max-width: 960px)"
  backdrop-color="hsla(0, 0%, 0%, 0.6)"
  collapsed="{{collapsed}}"
  opened="{{opened}}"
  on-change="_onSidebarChanged">

  <div slot="sidebar"></div>
  <div slot="content"></div>
</nebula-sidebar-layout>
```

*For more information on element properties and methods see the element API documentation.*

## Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request :D

## Change Log

See [CHANGELOG](/CHANGELOG.md)

## License

See [LICENSE](/LICENSE.md)