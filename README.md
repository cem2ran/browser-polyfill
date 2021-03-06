[![NPM](https://nodei.co/npm/@expo/browser-polyfill.png)](https://nodei.co/npm/@expo/browser-polyfill/)

---

# @expo/browser-polyfill

Browser polyfill for React Native - very beta feel free to contribute 😁💙

### Installation

```bash
yarn add @expo/browser-polyfill
```

### Usage

Import the library into your JavaScript file:

```js
import '@expo/browser-polyfill';
```

## Implements

## DOM

DOM is provided with very low support, these are used for libs like pixi.js that validate type.

```js
class Node
class Element
class Document
class HTMLImageElement
class Image
class HTMLVideoElement
class Video
class HTMLCanvasElement
class Canvas
```

### Image, HTMLImageElement

Image has support for loading callbacks, however the loaded uri must be passed to the src already.

```js
const image = new Image();
image.src = '';
image.onload = () => {
  const { src, width, height } = image;
};
image.addEventListener('loading', () => {});
image.addEventListener('error', () => {});
```

### Document

```js
const element = document.createElement('div');
const fakeContext = element.getContext('');
```

### Element

#### All sizes return the window size:

```js
element.clientWidth;
element.clientHeight;
element.innerWidth;
element.innerHeight;
element.offsetWidth;
element.offsetHeight;
```

#### Empty attributes that prevent libraries from crashing

```js
element.tagName;
element.addEventListener;
element.removeEventListener;
element.setAttributeNS;
element.createElementNS;
```

### Node

```js
node.ownerDocument;
node.className;
node.appendChild;
node.insertBefore;
node.removeChild;
node.setAttributeNS;
node.getBoundingClientRect;
```

# External Libraries

Some external node.js polyfills are added as well.

## [text-encoding](https://github.com/inexorabletash/text-encoding)

```
global.TextEncoder
global.TextDecoder
```

## [xmldom-qsa](https://github.com/zeligzhou/xmldom-qsa)

```
window.DOMParser
```

## [react-native-console-time-polyfill](https://github.com/MaxGraey/react-native-console-time-polyfill)

```
console.time(label);
console.timeEnd(label);
console.count(label);
```
