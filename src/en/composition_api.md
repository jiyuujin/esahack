# Composition API

Also in Vue2.0, you can install [@vue/composition-api](https://www.npmjs.com/package/@vue/composition-api) package.

⚠️ It's good for you to install the plugin gradually before you update to Vue3.0

```bash
# @vue/composition-api
yarn add @vue/composition-api
```

Import the plugin, and set `@/plugins/composition-api.ts` in Vue CLI.

```ts
import Vue from 'src/vue'
import CompositionApi from '@vue/composition-api'

Vue.use(CompositionApi)
```

You can write methods in `defineComponent`.

```ts
import { defineComponent, onMounted } from 'vue'

export default defineComponent({
    setup() {
        onMounted() {
            //
        }
        return {
            //
        }
    }
})
```
