# Web猫ブログ

Production started in Oct 2018, published in Nov 2018.

![](https://i.imgur.com/xuj6KVU.jpg)

## Technology stacks that make up the site

[Nuxt.js](https://ja.nuxtjs.org/guide/), which was `1.0.0rc11` at the time of production, was written in JavaScript, but later rewritten to TypeScript. The TypeScript API was also adopted from the `Decorator API`, but now the way to write `Options API` (Use `Vue.extend`) is progressing (it will be rewritten using the `Composition API` for Vue 3.0 soon)

Also, I am using the atomic component used in Admin and the plugin [@nekohack/j-stylebook](https://www.npmjs.com/package/@nekohack/j-stylebook) that was created and published to be shared with each other

- j-stylebook
- Nuxt.js
- Nuxt.js PWA
- Contentful
- AWS ECS
- AWS Fargate
- AWS Cloudfront
- Circle CI
- Github Actions

### Create model

Please confirm that you have registered in advance from the Contentful management screen. As soon as you register in advance, set the space `Nuxt blog`, the template `blog`, and the access token required to access the contentful data from the front-end framework (Nuxt.js)

```bash
contentful space create --name 'Nuxt blog'
contentful space seed --template blog
contentful space accesstoken create --name nuxt-blog
```

This time, the blog prepared the following models, and made each model a required item. Just make each field carefully below

| Column | Type |
|:---|:---|
| Title | string |
| Slug | string |
| Reaction | string |
| Hero image | string |
| Description | string |
| Body | string |
| Author | object |
| Publish Date | Date |
| Tags | Array<string> |
| Category | string |

### Use an endpoint

The setting is written in `.contentful.json` as a whole, but Nuxt.js creates a new `.env` and makes it accessible in `process.env`

```ts
module.exports = {
  env: {
    CTF_PERSON_ID: CONTENTFUL_CONFIG.CTF_PERSON_ID,
    CTF_BLOG_POST_TYPE_ID: CONTENTFUL_CONFIG.CTF_BLOG_POST_TYPE_ID,
    CTF_SPACE_ID: CONTENTFUL_CONFIG.CTF_SPACE_ID,
    CTF_CDA_ACCESS_TOKEN: CONTENTFUL_CONFIG.CTF_CDA_ACCESS_TOKEN,
  }
}
```

Now you can get contents by creation an instance with `createClient()`

```js
client
  .getEntries(contentfulOptions)
  .then(entries => {
    // console.log(entries)
  })
  .catch(console.error)
```

It's `CTF_PERSON_ID`, but don't worry because it works normally without setting

## A technical blog used `VuePress`

Before production, I was also considering the plan using `VuePress`. All markdown files in the same repository are included in `this.$site.pages`, so you can realize posting by selecting the required Markdown files as appropriate

```js
computed: {
  posts() {
    // console.log(this.$site.pages)
    return this.$site.pages
      .filter(page => page.path.startsWith('/_posts/'))
      .sort((a, b) => new Date(b.frontmatter.date) - new Date(a.frontmatter.date));
  },
},
```

It seems good to call the component from Markdown as follows.

```md
---
home: false
---

<Post />
```

## Reference

Japanese only, but I'm posting on the blog.

- [NuxtとContentfulで簡単ブログ生活](https://webneko.dev/posts/created-webneko-blog-used-nuxt-js-and-contentful)
- [VuePressをブログとして使う](https://webneko.dev/posts/enabled-to-post-a-blog-in-vuepress)
