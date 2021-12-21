# VSCode

## Install

[Visual Studio Code のダウンロード](https://code.visualstudio.com/download) からインストールウィザードの指示に従いインストールします。

## Use languages

- [Dart](dart.md)

### Use Node.js

[コード] - [設定] で `setting.json` を検索する。

- `eslint` 実行時に prettier を適用する
- ファイル保存時に ESLint のルールを自動的に適用する

```.json
{
    "prettier.eslintIntegration": true,
    "eslint.autoFixOnSave": true,
    "eslint.options": {
        "configFile": "./.eslintrc.js"
    },
    "eslint.validate": [
        "javascript",
        {
            "language": "typescript",
            "autoFix": true
        },
        {
            "language": "vue",
            "autoFix": true
        }
    ]
}
```
