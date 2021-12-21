# Composition API

また、Vue 2.0 では、[@vue/composition-api](https://www.npmjs.com/package/@vue/composition-api) パッケージをインストールできます。

⚠ ️Vue3.0 にアップデートする前に、プラグインを徐々にインストールすることをお勧めします

```bash
# @vue/composition-api
yarn add @vue/composition-api
```

プラグインをインポートし、VueCLIで `@/plugins/composition-api.ts` を設定します。

```ts
import Vue from 'src/vue'
import CompositionApi from '@vue/composition-api'

Vue.use(CompositionApi)
```

`defineComponent` でメソッドを書くことができます。

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
