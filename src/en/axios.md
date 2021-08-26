# `axios`

Install [axios](https://www.npmjs.com/package/axios) package.

You use `axios` in [Vue CLI](https://cli.vuejs.org/)

```ts
import {AxiosInstance} from 'src/en/axios'

declare module 'vue/types/vue' {
  interface Vue {
    $http: AxiosInstance
  }
}
```

You set the environment variable in `.env`

```ts
import _Vue from 'client/src/contents/vue'
import axios from 'src/en/axios'

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
