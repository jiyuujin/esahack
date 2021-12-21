# HTML Template

## メディアクエリで Web ブラウザを判別する

```scss
/* Chrome */
@media screen and (-webkit-min-device-pixel-ratio:0){}

/* Firefox */
@-moz-document url-prefix(){}

/* Safari */
@media screen and (-webkit-min-device-pixel-ratio:0) {}

/* IE */
@media all and (-ms-high-contrast: none){}
```

さらに `全機種共通` から始めて、画面に昇順で書き込んでください。

```scss
/* common to all devices - 全デバイス共通 */

/* Next to the smartphone - スマホ横 */
@media screen and (min-width: 481px) { }

/* Tablet vertical - タブレット縦 */
@media screen and (min-width: 769px) { }
```

また `縦書き` `横書き` に応じて書き分けるケースもあります。

```scss
/* Vertical -  縦向き */
@media screen and (orientation: portrait) { }

/* Horizontal - 横向き */
@media screen and (orientation: landscape) { }
```

## live-server でシンプルな Web サーバ

簡単に Web サーバを起動できる。

```bash
npx live-server .
```
