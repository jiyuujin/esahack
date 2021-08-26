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
  import {ComponentOptions} from 'src/en/vue'
  const component: ComponentOptions
  export default component
}
```

## Vue `2.x`

At first, you must create an entry point.

```ts
import Vue from 'src/en/vue'
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
import Vue from 'src/en/vue'
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
import Vue from 'src/en/vue'
import Vuex, {StoreOptions} from 'vuex'

// Modules
import {product} from './product'

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
  import Vue from 'src/en/vue'
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

- [Options API](en/options_api.md)
- [Composition API](en/composition_api.md)

## Use plugins

Let's use what you can.

- [axios](en/axios.md)
- [sanitize-html](en/sanitize-html.md)
- [vue-cookie-law](vue-cookie-law.md)
- [vue-datetimerange-picker](vue-datetimerange-picker.md)
- [vue-fontawesome](vue-fontawesome.md)
- [vue-image-lightbox](vue-image-lightbox.md)
- [vue-single-picker](vue-single-picker.md)

## Repositories

- [https://github.com/nekohack-oss/nuxt](https://github.com/nekohack-oss/nuxt)
- [https://github.com/nekohack-oss/vue3-cli](https://github.com/nekohack-oss/vue3-cli)
- [https://github.com/nekohack-oss/vue2-cli](https://github.com/nekohack-oss/vue2-cli)
