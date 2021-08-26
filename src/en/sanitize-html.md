# `sanitize-html`

Install [sanitize-html](https://www.npmjs.com/package/sanitize-html) package

To defence from the attack by XSS, set `$sanitize` in prototype

```ts
import Vue from 'src/vue'
import sanitizeHTML from 'src/en/sanitize-html'

Vue.prototype.$sanitize = sanitizeHTML
```

Use `$sanitize` in `v-html`

```html
<!-- use `$sanitize` in `v-html` -->
<div v-html="$sanitize(items.description)" />
```
