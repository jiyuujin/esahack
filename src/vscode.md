# VSCode

## Install

Install according to the instructions of the installation wizard　from [Download Visual Studio Code](https://code.visualstudio.com/download)

## Use languages

- [Dart](dart.md)

### Use Node.js

Search `setting.json` at [Code] - [Settings]

- Apply prettier when run `eslint`
- Automatically apply the ESLint rules when save files

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
