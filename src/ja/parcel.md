# Parcel usage

`package.json` のみを書き込む。基本的には、url をエントリポイントとして `parcel` コマンドを実行します。

```json
{
  "scripts": {
    "parcel": "parcel build ./public/index.html --no-minify --public-url .",
    "parcel:w": "parcel ./parcel/index.html"
  }
}
```

## Repositories

- [https://github.com/nekohack-oss/parcel](https://github.com/nekohack-oss/parcel)
