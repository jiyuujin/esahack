# Parcel usage

Write only `package.json`. Basically, you run `parcel` command with a url as the entry point.

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
