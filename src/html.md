# HTML Template

## Determine web browser with media query

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

In addition, start with `common to all devices` and write in ascending order on the screen

```scss
/* common to all devices - 全デバイス共通 */

/* Next to the smartphone - スマホ横 */
@media screen and (min-width: 481px) { }

/* Tablet vertical - タブレット縦 */
@media screen and (min-width: 769px) { }
```

There is also a case of writing according to `vertical` / `horizontal`

```scss
/* Vertical -  縦向き */
@media screen and (orientation: portrait) { }

/* Horizontal - 横向き */
@media screen and (orientation: landscape) { }
```

## Simple web server with live-server

Easily start a web server

```bash
npx live-server .
```
