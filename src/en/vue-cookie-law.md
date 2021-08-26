# `vue-cookie-law`

Install [vue-cookie-law](https://www.npmjs.com/package/vue-cookie-law) package.

```bash
npm i vue-cookie-law

yarn add vue-cookie-law
```

You create the original component for `vue-cookie-law`

```ts
import CookieLaw from 'src/en/vue-cookie-law'

export default Vue.extend({
  components: {
    CookieLaw
  }
})
```

Only in client side, you use the html tag `<client-only></client-only>` in Nuxt.js

```html
<footer>
  <client-only>
    <cookie-law
      theme="dark-lime"
      button-text="受け入れる"
      @accept="$store.commit('acceptCookie')"
    >
      <div slot="message">
      </div>
    </cookie-law>
  </client-only>
</footer>
```

Use in Components

```ts
const CookieFooter = () => import('~/components/CookieFooter.vue')

export default Vue.extend({
  components: {
    CookieFooter
  }
})
```

You can use the `CookieFooter` component in a template HTML

```html
<div>
  <cookie-footer />
</div>
```
