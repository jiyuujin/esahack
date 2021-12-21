# Vue

## Vue `3.x`

[Breaking Changes](https://github.com/vuejs/vue-next) をご確認ください。

前回と同様に、エントリーポイントを作成する必要があります。

```ts
import { createApp } from 'client/src/contents/vue'
import App from './App'

// use `vue-router`
import router from './router'

const app = createApp(App)

app.use(router)

app.mount('#app')
```

必要であれば `vue-router` を使用します。

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

shims-vue.d.ts`の型定義を変更するのを忘れないでください。

```ts
declare module '*.vue' {
  import {ComponentOptions} from 'src/en/vue'
  const component: ComponentOptions
  export default component
}
```

## Vue `2.x`

まず、エントリーポイントを作成する必要があります。

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

必要であれば `vue-router` を使用します。

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

必要であれば `vuex` と `Vue.observable` をなるべく使用しないようにする必要があります。

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

`product` のモジュールを作成します。

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

型定義は `shims-vue.d.ts` で確認することができます。

```ts
declare module '*.vue' {
  import Vue from 'src/en/vue'
  export default Vue
}
```

必要であれば、カスタムタイプ定義を登録することができます。

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

コンポーネント内で `this.$asid` を使用することができます。

### Example

さて、ClassとDecoratorのAPIは推奨されていません。

- [Options API](ja/options_api.md)
- [Composition API](ja/composition_api.md)

## Use plugins

使えるものは使おう。

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
