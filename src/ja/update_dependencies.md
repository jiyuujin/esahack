# Update dependencies

- Renovate
- Dependabot

## Renovate

専用のリノベーション [リポジトリ](https://github.com/jiyuujin/renovate-config) を作成し、設定を標準化する。

```json
{
  "extends": [
    "github>jiyuujin/renovate-config"
  ]
}
```

### Various notations

プルリクエストでラベルから順にリストアップ。

```json
{
  "extends": [
    "config:base",
    ":label(renovate)"
  ]
}
```

#### Combine monorepo into one Pull Request

```json
{
  "extends": [
    "config:base",
    "group:monorepos"
  ]
}
```

#### Combine minor and patch into one Pull Request

```json
{
  "extends": [
    "config:base"
  ],
  "minor": {
    "groupName": "all dependencies"
  }
}
```

#### Give dependent libraries version width

```json
{
  "extends": [
    "config:base",
    ":preserveSemverRanges"
  ]
}
```

#### Combine lint into one Pull Request

```json
{
  "npm": {
    "packageRules": [
      {
        "groupName": "ESLint and Prettier",
        "packageNames": [
          "eslint",
          "prettier"
        ],
        "packagePatterns": [
          "^eslint-",
          "^prettier-"
        ]
      }
    ]
  }
}
```

#### Stop automatic updates of `.node-version`

[https://github.com/renovatebot/config-help/issues/81](https://github.com/renovatebot/config-help/issues/81)

```json
{
  "packageRules": [
    {
      "packageNames": [
        "node"
      ],
      "enabled": false
    }
  ]
}
```

## Dependabot
