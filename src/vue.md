# Vue

## Vue `3.x`

Breaking changes, please confirm [https://github.com/vuejs/vue-next](https://github.com/vuejs/vue-next)

As before, you must create an entry point.

```ts
import { createApp } from 'client/src/contents/vue'
import App from './App'

// use `vue-router`
import router from './router'

const app = createApp(App)

app.use(router)

app.mount('#app')
```

If necessary use `vue-router`

```ts
import { createRouter, createWebHistory } from 'vue-router'

import HelloWorld from '../components/HelloWorld'

const routes = [
  {
    path: '/',
    name: 'HelloWorld',
    component: HelloWorld
  }
]

const router = createRouter({
  history: createWebHistory(),
  linkActiveClass: 'active',
  routes
})

export default router
```

### Use TypeScript in Vue `3.x`

Don't forget change the type definition in `shims-vue.d.ts`.

```ts
declare module '*.vue' {
  import { ComponentOptions } from 'vue'
  const component: ComponentOptions
  export default component
}
```

## Vue `2.x`

At first, you must create an entry point.

```ts
import Vue from 'vue'
import App from './App.vue'

// use `vue-router`
import router from './router'

const vm = new Vue({
    render: h => h(App),
    router,
}).$mount('#app')
```

If necessary use `vue-router`

```ts
import Vue from 'vue'
import Router from 'vue-router'

import HelloWorld from '../components/HelloWorld'

Vue.use(Router)

const routes = [
  {
    path: '/',
    name: 'HelloWorld',
    component: HelloWorld
  }
]

export default new Router({
  mode: 'history',
  base: process.env.BASE_URL,
  routes: routes
})
```

If necessary use `vuex`, you must not use `vuex` and `Vue.observable` as much as possible.

```ts
import Vue from 'vue'
import Vuex, { StoreOptions } from 'vuex'

// Modules
import { product } from './product'

Vue.use(Vuex)

type RootState = {
  version: string
}

const store: StoreOptions<RootState> = {
  modules: {
    product: product
  },
  state: {
    version: '1.0.0'
  }
}

export const createStore = () => {
  return new Vuex.Store<RootState>(store)
}
```

You create the module for `product`.

```ts
import { Module, ActionTree, MutationTree } from 'vuex'

const namespaced = true

type RootState = {
  version: string
}

export const state = (): State => ({
  isCookieAccepted: false
})

export interface State {
  isCookieAccepted: boolean | false
}

export const mutations: MutationTree<State> = {
  acceptCookie(state) {
    state.isCookieAccepted = true
  }
}

export const actions: RootActionTree<State, RootState> = {
  accept(flag) {
    this.commit('product/acceptCookie', flag)
  }
}

export interface RootActionTree<State, RootState>
  extends ActionTree<State, RootState> {
  //
}

export const getters = {
  //
}

export const product: Module<State, RootState> = {
  namespaced,
  state,
  mutations,
  actions,
  getters
}
```

## Use TypeScript in Vue

You can confirm the type definition in `shims-vue.d.ts`.

```ts
declare module '*.vue' {
  import Vue from 'vue'
  export default Vue
}
```

If necessary you can register the custom type definition.

```ts
interface MyWindow extends Window {
  asid: any
}

declare let window: MyWindow

declare module 'vue/types/vue' {
  interface Vue {
    $asid: any
  }
}

export default window
```

You can use `this.$asid` in components.

### Example

Now, the Class and Decorator API aren't recommended.

- [Options API](options_api.md)
- [Composition API](composition_api.md)

## Use plugins

Let's use what you can.

- `axios`
- `fontawesome`
- `vue-image-box`
- `vue-cookie-law`
- `vue-datetimerange-picker`
- `vue-single-picker`
- `sanitize-html`

### `axios`

Install [axios](https://www.npmjs.com/package/axios) package.

You use `axios` in [Vue CLI](https://cli.vuejs.org/)

```ts
import { AxiosInstance } from 'axios'

declare module 'vue/types/vue' {
  interface Vue {
    $http: AxiosInstance
  }
}
```

You set the environment variable in `.env`

```ts
import _Vue from 'client/src/contents/vue'
import axios from 'axios'

export default {
  install(Vue: typeof _Vue): void {
    const http = axios.create({
      baseURL: process.env.VUE_APP_BASE_API,
      timeout: 10000
    })
    http.interceptors.request.use((config: any) => {
      config.headers.common['X-Requested-With'] = 'XMLHttpRequest'
      return config
    })
    Vue.prototype.$http = http
  }
}
```

Use in Components

```ts
import Vue from 'vue'

export default Vue.extend({
  methods: {
    async fetchUsers() {
      await this.$http
        .get('/users', { params: this.searchForm })
        .then((res: any) => {
          this.users = res.data
        })
        .catch((err: any) => {
          console.error(err)
        })
  }
})
```

### `fortawesome`

- Install [@fortawesome/fontawesome-svg-core](https://www.npmjs.com/package/@fortawesome/fontawesome-svg-core) package.
- Install [@fortawesome/free-solid-svg-icons](https://www.npmjs.com/package/@fortawesome/free-solid-svg-icons) package.
- Install [@fortawesome/vue-fontawesome](https://www.npmjs.com/package/@fortawesome/vue-fontawesome) package.

You use `@fortawesome/fontawesome-svg-core` in [Vue CLI](https://cli.vuejs.org/)

```ts
import Vue from 'vue'

import { library } from '@fortawesome/fontawesome-svg-core'

// Regular, Light, and Brands are existed
import {
  faCoffee,
  fas,
  faQuestion,
  faQuestionCircle,
  faPlus,
  faMinus,
  faCalendar,
  faAngleDown,
  faHome,
  faExclamationCircle,
  faBuilding,
  faUser,
  faKeyboard,
  faWallet,
  faMoneyBillWaveAlt,
  faPuzzlePiece,
  faTh,
  faBell,
  faUserCircle,
  faCheckCircle
} from '@fortawesome/free-solid-svg-icons'

import {
  FontAwesomeIcon,
  FontAwesomeLayers,
  FontAwesomeLayersText
} from '@fortawesome/vue-fontawesome'

library.add(faCoffee)
library.add(fas)
library.add(faQuestion)
library.add(faQuestionCircle)
library.add(faPlus)
library.add(faMinus)
library.add(faCalendar)
library.add(faAngleDown)
library.add(faHome)
library.add(faExclamationCircle)
library.add(faBuilding)
library.add(faUser)
library.add(faKeyboard)
library.add(faWallet)
library.add(faMoneyBillWaveAlt)
library.add(faPuzzlePiece)
library.add(faTh)
library.add(faBell)
library.add(faUserCircle)
library.add(faCheckCircle)

Vue.component('font-awesome-icon', FontAwesomeIcon)
// Vue.component('font-awesome-layers', FontAwesomeLayers)
// Vue.component('font-awesome-layers-text', FontAwesomeLayersText)
```

Use `font-awesome-icon` tag

```html
<!-- use `font-awesome-icon` tag -->
<font-awesome-icon icon="check-circle" />
```

### `vue-image-lightbox`

Install [vue-image-lightbox](https://www.npmjs.com/package/vue-image-lightbox) package.

```bash
npm i vue-image-lightbox vue-lazyload

yarn add vue-image-lightbox vue-lazyload
```

⚠️ Not used TypeScript, you need to set the original type definition.

Use `require('')` not bad, but

```ts
// use `require('')`
const ImageLightbox = require('vue-image-light-box')
```

Also not bad, but

```ts
// @ts-ignore
import ImageLightbox from 'vue-image-lightbox'
```

Set the original type definition, you need to set the original type definition

```ts
type Media = Array<{
  thumb: string
  sources: Array<{
    src: string
    type: string
  }>
  caption: string
  type?: string
  width?: number
  height?: number
  autoplay?: boolean
}>

declare module 'vue-image-lightbox' {
  interface ImageLightbox {
    media: Media
    showLightBox?: boolean
    startAt?: number
    nThumbs?: number
    showThumbs?: boolean
    autoPlay?: boolean
    autoPlayTime?: number
    siteLoading?: boolean | null
    showCaption?: boolean
    disableScroll?: boolean
    lengthToLoadMore?: number
    closable?: boolean
    closeText?: string
    previousText?: string
    nextText?: string
    previousThumbText?: string
    nextThumbText?: string
  }
  export function nextImage(): void;
  export function previousImage(): void;
  export function closeLightBox(): void;
  export function showImage(index: number): void;
}
```

### `vue-cookie-law`

Install [vue-cookie-law](https://www.npmjs.com/package/vue-cookie-law) package.

```bash
npm i vue-cookie-law

yarn add vue-cookie-law
```

You create the original component for `vue-cookie-law`

```ts
import CookieLaw from 'vue-cookie-law'

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

### `vue-datetimerange-picker`

Install [vue-datetimerange-picker](https://www.npmjs.com/package/vue-datetimerange-picker) package

```bash
npm i vue-datetimerange-picker

yarn add vue-datetimerange-picker
```

You can use as general CSS frameworks

```js
import Vue from 'vue'
import { CoreUI } from 'vue-datetimerange-picker'
import 'vue-datetimerange-picker/dist/vue-range-picker.css'

Vue.use(CoreUI)
```

#### Props

```html
<v-range-picker
    ref="range-picker"
    :show-dropdown="showDropdown"
    :auto-apply="autoApply"
    :linked-calendars="linkedCalendars"
    :date-range="dateRange"
    :opens="opens"
    :date-format="dateFormat"
    @update="updateValues"
    @toggle="checkOpen"
>
    <div slot="input" slot-scope="picker" style="min-width: 350px;">
        {{ picker.startDate }} - {{ picker.endDate }}
    </div>
</v-range-picker>
```

`dateRange` is required, but set custom ranges in `ranges`

| # | Type | Default |
|:---|:---|:---|
| minDate | `Date` | `` |
| maxDate | `Date` | `` |
| linkedCalendars | `Boolean` | `true` |
| showDropdown | `Boolean` | `false` |
| dateRange | `Object` | `` |
| ranges | `Object` | `` |
| localeData | `Object` | `` |
| opens | `String` | `center` ( `left` / `right` ) |
| dateFormat | `Boolean` | `true` |
| timePicker | `Boolean` | `false` |
| timePickerIncrement | `Number` | `5` |
| timePicker24Hour | `Boolean` | `true` |
| timePickerSeconds | `Boolean` | `false` |

### `vue-single-picker`

Install [vue-single-picker](https://www.npmjs.com/package/vue-single-picker) package.

```bash
npm i vue-single-picker

yarn add vue-single-picker
```

You can use as general CSS frameworks

```js
import Vue from 'vue'
import { CoreUI } from 'vue-single-picker'
import 'vue-single-picker/dist/vue-single-picker.css'

Vue.use(CoreUI)
```

#### Props

```html
<v-single-picker
    ref="single-picker"
    :show-dropdown="showDropdown"
    :auto-apply="autoApply"
    :linked-calendars="linkedCalendars"
    :date="date"
    :opens="opens"
    :date-format="dateFormat"
    @update="updateValues"
    @toggle="checkOpen"
>
    <div slot="input" slot-scope="picker" style="min-width: 350px;">
        {{ picker }}
    </div>
</v-single-picker>
```

`date` is required, please format in `dayjs` plugin

| # | Type | Default |
|:---|:---|:---|
| minDate | `Date` | `` |
| maxDate | `Date` | `` |
| linkedCalendars | `Boolean` | `true` |
| showDropdown | `Boolean` | `false` |
| date | `string` | `` |
| localeData | `Object` | `` |
| opens | `String` | `center` ( `left` / `right` ) |
| dateFormat | `Boolean` | `true` |

### `sanitize-html`

Install [sanitize-html](https://www.npmjs.com/package/sanitize-html) package

To defence from the attack by XSS, set `$sanitize` in prototype

```ts
import Vue from 'vue'
import sanitizeHTML from 'sanitize-html'

Vue.prototype.$sanitize = sanitizeHTML
```

Use `$sanitize` in `v-html`

```html
<!-- use `$sanitize` in `v-html` -->
<div v-html="$sanitize(items.description)" />
```

## Repositories

- [https://github.com/nekohack-oss/nuxt](https://github.com/nekohack-oss/nuxt)
- [https://github.com/nekohack-oss/vue3-cli](https://github.com/nekohack-oss/vue3-cli)
- [https://github.com/nekohack-oss/vue2-cli](https://github.com/nekohack-oss/vue2-cli)
