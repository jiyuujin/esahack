# VSCode

## Use Node.js

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
