# Webpack usage

`webpack.config.js` を書く。

## Use frameworks such as Vue 3 and React

[Nuxt.js](https://ja.nuxtjs.org/) 、[Gatsby.js](https://www.gatsbyjs.org/) などの一般的なフレームワークでは、通常 `webpack` プラグインを使用しています。意識しなくても使えるのですが、せめて`webpack`プラグインはどう使うのでしょうか？

### Use Vue 3

リポジトリ、[https://github.com/jiyuujin/vue-next-webpack-preview](https://github.com/jiyuujin/vue-next-webpack-preview) を確認してください。

[Nuxt.js](https://ja.nuxtjs.org/) 、 [Vue CLI](https://cli.vuejs.org/) を利用することができます。

```js
const path = require('path')
const { VueLoaderPlugin } = require('vue-loader')

module.exports = (env = {}) => ({
    resolve: {
        alias: {
            'vue': '@vue/runtime-dom',
        }
    },
    module: {
        rules: [
            {
                test: /\.ts$/,
                exclude: /node_modules/,
                loader: 'ts-loader',
                options: {
                    appendTsSuffixTo: [/\.vue$/]
                }
            },
            {
                test: /\.vue$/,
                use: 'vue-loader'
            },
        ]
    },
    plugins: [
        new VueLoaderPlugin(),
    ],
})
```

### Correspond to TypeScript in React

`TypeScript` の導入に対応する必要があります。

```js
const path = require('path')

module.exports = {
    module: {
        rules: [
            {
                test: /\.(js|jsx)$/,
                exclude: /node_modules/,
                use: ['babel-loader'],
            },
            {
                test: /\.(ts|tsx)$/,
                use: [
                    {
                        loader: 'ts-loader',
                        options: {
                            configFile: path.resolve(
                                __dirname,
                                'tsconfig.json'
                            ),
                            happyPackMode: true,
                            transpileOnly: true,
                        },
                    },
                ],
            },
        ],
    },
}
```

#### Load JSX files

`babel-loader` をロードすることで、JSX ファイルを利用することができます。

```js
module.exports = {
    module: {
        rules: [
            {
                test: /\.(js|jsx)$/,
                exclude: /node_modules/,
                use: ['babel-loader'],
            },
        ],
    },
}
```

## Load and minify CSS files

CSSファイルは `css-loader` と `sass-loader` をロードして利用し、 `optimize-css-assets-webpack-plugin` をロードして最小化することができます。

```js
const path = require('path')
const MiniCssExtractPlugin = require('mini-css-extract-plugin')
const OptimizeCSSAssetsPlugin = require('optimize-css-assets-webpack-plugin')

const isDev = process.env.NODE_ENV !== 'production'

module.exports = {
    module: {
        rules: [
            {
                test: /\.css$/,
                use: [
                    {
                        loader: MiniCssExtractPlugin.loader
                    },
                    {
                        loader: 'css-loader',
                        options: {
                            // オプションでCSS内のurl()を取り込む
                            url: true,
                            // ソースマップの利用有無
                            sourceMap: isDev,
                            // 0 => no loaders (default)
                            // 1 => postcss-loader
                            // 2 => postcss-loader, sass-loader
                            importLoaders: 2
                        }
                    }
                ]
            },
            {
                test: /\.scss$/,
                use: [
                    {
                        loader: MiniCssExtractPlugin.loader
                    },
                    {
                        loader: 'css-loader',
                        options: {
                            // オプションでCSS内のurl()を取り込む
                            url: true,
                            // ソースマップの利用有無
                            sourceMap: isDev,
                            // 0 => no loaders (default)
                            // 1 => postcss-loader
                            // 2 => postcss-loader, sass-loader
                            importLoaders: 2
                        }
                    },
                    {
                        loader: 'sass-loader',
                        options: {
                            sourceMap: isDev
                        }
                    }
                ]
            }
        ]
    },
    plugins: [
        new MiniCssExtractPlugin({
            filename: 'bundle.css'
        })
    ],
    optimization: {
        minimizer: [
            new OptimizeCSSAssetsPlugin()
        ]
    }
}
```

## Repositories

- [https://github.com/nekohack-oss/webpack5-react](https://github.com/nekohack-oss/webpack5-react)
- [https://github.com/nekohack-oss/webpack4-react](https://github.com/nekohack-oss/webpack4-react)
- [https://github.com/nekohack-oss/webpack5-preact](https://github.com/nekohack-oss/webpack5-preact)
- [https://github.com/nekohack-oss/webpack4-preact](https://github.com/nekohack-oss/webpack4-preact)
- [https://github.com/nekohack-oss/webpack5-vue3](https://github.com/nekohack-oss/webpack5-vue3)
- [https://github.com/nekohack-oss/webpack4-vue2](https://github.com/nekohack-oss/webpack4-vue2)
