# Parvus

An accessible, open-source image lightbox with no dependencies.

[Open in CodePen](https://codepen.io/collection/DwLBpz)

## Table of contents

- [Features](#features)
- [Get Parvus](#get-parvus)
  - [Download](#download)
  - [Package managers](#package-managers)
- [Usage](#usage)
- [Options](#options)
- [API](#api)
- [Events](#events)
- [Browser support](#browser-support)

## Features

- Accessible
- API
- Events

## Get Parvus

### Download

CSS: `dist/css/parvus.min.css` minified, or `dist/css/parvus.css` un-minified

JavaScript: `dist/js/parvus.min.js` minified, or `dist/js/parvus.js` un-minified

### Package managers

Parvus is also available on npm.

`npm install parvus --save`

## Usage

You can install Parvus by linking the `.css` and `.js` files to your HTML file. The HTML code may look like this:

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Page title</title>

  <!-- CSS -->
  <link href="path/to/parvus.min.css" rel="stylesheet">
</head>
<body>
  <!-- HTML content -->

  <!-- JS -->
  <script src="path/to/parvus.min.js"></script>
</body>
</html>
```

The standard way of using Parvus is a linked thumbnail image with the class name `lightbox` to a larger image:

```html
<a href="path/to/image.jpg" class="lightbox">
  <img src="path/to/thumbnail.jpg" alt="">
</a>
```

Initialize the script by running:

```js
const prvs = new Parvus()
```

## Options

You can pass an object with custom options as an argument.

```js
const prvs = new Parvus({
  scrollClose: false
})
```

The following options are available:

| Property | Type | Default | Description |
| --- | --- | --- | --- |
| selector | string | ".lightbox" | All elements with this class triggers Parvus |
| lightboxLabel | string | "..." | ARIA label for screen readers |
| lightboxLoadingIndicatorLabel | string | "..." | ARIA label for screen readers |
| lightboxIndicatorIcon | string | "..." | SVG icon for the lightbox indicator |
| closeButtonIcon | string | "..." | SVG icon for the close button |
| closeButtonLabel | string | "..." | ARIA label for screen readers |
| docClose | bool | true | Click outside to close Parvus |
| scrollClose | bool | false | Scroll to close Parvus |
| swipeClose | bool | true | Swipe up to close Parvus |
| threshold | number | 100 | Touch dragging threshold (in px) |
| transitionDuration | number | 300 | Specifies how many milliseconds (ms) the transition effects takes to complete |
| transitionTimingFunction | string | "..." | Specifies the speed curve of the transition effects |

## API

| Function | Description |
| --- | --- |
| `open(element)` | Open `element` (DOM element) |
| `close()` | Close Parvus |
| `add(element)` | Add `element` (DOM element) |
| `remove(element)` | Remove `element` (DOM element) |
| `isOpen()` | Check if Parvus is open |
| `destroy()` | Destroy Parvus |

## Events

Bind events with the `.on()` and `.off()` methods.

```js
const prvs = new Parvus()

const listener = function listener () {
  console.log('eventName happened')
}

// bind event listener
prvs.on(eventName, listener)

// unbind event listener
prvs.off(eventName, listener)
```

| eventName | Description |
| --- | --- |
| `open` | Triggered after Parvus has been opened |
| `close` | Triggered after Parvus has been closed |
| `destroy` | Triggered after Parvus has been destroyed |

## Browser support

Parvus supports the following browser (all the latest versions):

- Chrome
- Edge
- Firefox
- Safari

Use the [`:focus-visible` polyfill](https://github.com/WICG/focus-visible) to support Safari and other Browsers.
