[![Published on webcomponents.org](https://img.shields.io/badge/webcomponents.org-published-green.svg)](https://www.webcomponents.org/element/arsnebula/nebula-sidebar-layout)
[![Polymer Version](https://img.shields.io/badge/polymer-v2-blue.svg)](https://www.polymer-project.org)
[![Sauce Labs Build Status](https://img.shields.io/badge/saucelabs-passing-red.svg)](https://saucelabs.com/beta/builds/161b7bd94daa49acbdc87f52e4dd1dc7)
[![Gitter Chat](https://badges.gitter.im/org.png)](https://gitter.im/arsnebula/webcomponents)
[![Become a Patreon](https://img.shields.io/badge/patreon-support_us-orange.svg)](https://www.patreon.com/arsnebula)

# \<nebula-sidebar-layout\>

A responsive sidebar layout.

* Two-column application layout using slots
* Fixed sidebar container on the left, fluid content container on the right
* Sidebar collapses to a drawer menu at a configurable breakpoint
* Automatically makes the content container `inert` when the drawer is open
* Easily customized using CSS custom variables, mixins or style properties

> Warning: This element supports [Inert Subtrees](https://html.spec.whatwg.org/multipage/interaction.html#inert-subtrees), a draft feature of HTML which may not be supported by all browsers. To ensure support by all browsers, consider using the [Inert Polyfill](https://github.com/GoogleChrome/inert-polyfill).

> Warning: This element requires the [Web Animations API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Animations_API), a draft feature of HTML which may not be supported by all browsers. To ensure support by all browsers, consider using the [Web Animations Polyfill](https://github.com/web-animations/web-animations-js).


## Installation

```sh
$ bower install -S arsnebula/nebula-sidebar-layout
```

## Getting Started

Import the element:

```html
<link rel="import" href="/bower_components/nebula-sidebar-layout/nebula-sidebar-layout.html"> 
```

The element utilizes offscreen positioning for the drawer when collapsed, so the `body` and and other parent elements should be set to fill the browser screen. The following is a sample stylesheet for ensuring the body matches the viewport.

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

Add the element.

```html
<nebula-sidebar-layout
  breakpoint="(max-width: 960px)"
  collapsed="{{collapsed}}"
  opened="{{opened}}"
  on-changed="_onChanged">

  <div slot="sidebar"></div>
  <div slot="content"></div>
</nebula-sidebar-layout>
```

Style the element.

```css
nebula-sidebar-layout {
  --nebula-sidebar-layout-backdrop-color: hsla(0, 0%, 0%, 0.6);
  --nebula-sidebar-layout-transition-duration: 0.25s;
  --nebula-sidebar-layout-sidebar: {
    border-right: 1px solid silver;
  }
}
```

*For more information, see the API documentation.*

## Contributing

We welcome and appreciate feedback from the community. Here are a few ways that you can show your appreciation for this package:

* Give us a **Star on GitHub** from either [webcomponents.org](https://www.webcomponents.org/element/arsnebula/nebula-element-mixin) or directly on [GitHub](https://github.com/arsnebula/nebula-element-mixin).

* Submit a feature request, or a defect report on the [Issues List](https://www.webcomponents.org/element/arsnebula/nebula-element-mixin/issues).

* Become a [Patreon](https://www.patreon.com/arsnebula). It takes a lot of time and effort to develop, document, test and support the elements in our [Nebula Essentials](https://www.webcomponents.org/collection/arsnebula/nebula-essentials) collection. Your financial contribution will help ensure that our entire collection continues to grow and improve.

If you are a developer, and are interested in making a code contribution, consider opening an issue first to describe the change, and discuss with the core repository maintainers. Once you are ready, prepare a pull request:

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request :D

## Change Log

See [CHANGELOG](/CHANGELOG.md)

## License

See [LICENSE](/LICENSE.md)