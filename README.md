# Hot Module Replaceable Custom Element

Hot Module Replacement (HMR) is a feature commonly found in JS dev servers such as Webpack that allows a JS module to be reloaded dyanmically in the page without reloading the browser. It works well with most objects except for Custom Elements. Custom Elements need to be registered with the browsers `CustomElementRegistry` and cannot be reloaded or re-defined within it. Calling `customElements.define` on a tag that already exists will result in an error. This util, when HMR is enabled, will replace the prototypes of the existing instances of the custom element on the page and force a re-render.

[Learn more about HMR](https://webpack.js.org/concepts/hot-module-replacement/)

## Usage

```js
import { register } from '@polleverywhere/hmr-custom-element'

class MyElement extends HTMLElement {
}

register(module, 'my-element', MyElement)
```
