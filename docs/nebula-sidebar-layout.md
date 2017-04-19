# \<nebula-sidebar-layout\>

`<nebula-sidebar-layout>` is a web component to display a collapsable sidebar layout.

The element will automatically fill the parent container. It provides two named slots, `sidebar` and `content` configured as a horizontal flexbox. Using the `breakpoint` property, a media query will be monitored that will set the element `collapsed` property. When `collapsed` is true, the `sidebar` slot is changed to an offscreen fixed position container. The sidebar can be displayed using the `opened` property, and will overlay the `content` slot as an animated drawer with a backdrop.

# Import

```sh
$ bower install -S arsnebula/nebula-sidebar-layout
```

## Usage

The element uses offscreen positioning for the sidebar when collapsed. It can only be used effectively if the parent container fills the entire browser window. The following is a typical base style to ensure that the HTML `body` element is sized to fit the browser screen height and width.

```css
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
```

The element displays a two-column side-by-side layout with a fixed width sidebar on the left, and a fluid content container on the right. Content is inserted into each column using the `sidebar` and `content` named slots. The `breakpoint` property enables a media query that will set the element `collapsed` property. When `collapsed` is true, the `sidebar` slot is changed to an offscreen fixed position container. The sidebar can be displayed using the `opened` property, and will overlay the `content` slot as an animated drawer with a backdrop.

```html
<nebula-sidebar-layout
  breakpoint="(max-width: 960px)"
  collapsed="{{collapsed}}"
  opened="{{opened}}"
  on-opened-changed="_onOpenedChanged">
  <div slot="sidebar"></div>
  <div slot="content"></div>
</nebula-sidebar-layout>
```

The sidebar container width is set to `fit-content`. To specify the width of the sidebar, set a fixed width on the sidebar slot content.

```css
<style>
  nebula-sidebar-layout [slot=sidebar] {
    width: 280px;
  }
</style>
```

The `breakpoint` property specifies the media query that determines when the sidebar is collapsed. The default value collapses the sidebar when the browser screen width is less than 960px. To manually control the collapse of the sidebar, set the `breakpoint` to empty, and then toggle the `collapsed` property value manually.

```html
<nebula-sidebar-layout breakpoint collapsed="{{collapsed}}">
</nebula-sidebar-layout>
```

The element includes optional gesture support for opening and closing the sidebar by swiping left and right on touchscreen devices. Some mobile browsers use this gesture to switch browser tabs, so gesture support is disabled by default. To enable gesture support (such as for Cordova or Electron apps), set the `gesturesEnabled' property to `true`.

```html
<nebula-sidebar-layout gestures-enabled>
</nebula-sidebar-layout>
```

## Style

The element can be styled using standard CSS properties and the following CSS variables:

Custom property | Description | Default
:--- | :--- | :---
`--nebula-sidebar-layout-backdrop-color` | The color of the backdrop. | hsla(0, 0%, 0%, 0.6)

The element also inherits default values from the following global theme styles. If a global theme variable has not been set, it will use the local default.

Custom property | Description
:--- | :---
`--nebula-ui-backdrop-color` | The background color of the backdrop pseudo element.

## API Reference

### Properties

#### opened : Boolean (*notify, reflectToAttribute, default=false*)

Indicates if the element is opened.

#### collapsed : Boolean (*notify, reflectToAttribute, default=false*) {

Indicates if the element is collapsed.

#### breakpoint : String (*default=(max-width: 960px)*)

The media query to monitor as the breakpoint for element collapse.

### Events

#### collapsed-changed : CustomEvent

Event triggered when the property value of `collapsed` is changed.

#### opened-changed : CustomEvent

Event triggered when the property value of `opened` is changed.

### Class Extensions

### Behaviors / Mixins

#### [Nebula.ElementMixin](https://www.webcomponents.org/element/arsnebula/nebula-element-mixin)