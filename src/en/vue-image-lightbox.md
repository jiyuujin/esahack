# `vue-image-lightbox`

Install [vue-image-lightbox](https://www.npmjs.com/package/vue-image-lightbox) package.

```bash
npm i vue-image-lightbox vue-lazyload

yarn add vue-image-lightbox vue-lazyload
```

⚠️ Not used TypeScript, you need to set the original type definition.

Use `require('')` not bad, but

```ts
// use `require('')`
const ImageLightbox = require('vue-image-light-box')
```

Also not bad, but

```ts
// @ts-ignore
import ImageLightbox from 'src/en/vue-image-lightbox'
```

Set the original type definition, you need to set the original type definition

```ts
type Media = Array<{
  thumb: string
  sources: Array<{
    src: string
    type: string
  }>
  caption: string
  type?: string
  width?: number
  height?: number
  autoplay?: boolean
}>

declare module 'vue-image-lightbox' {
  interface ImageLightbox {
    media: Media
    showLightBox?: boolean
    startAt?: number
    nThumbs?: number
    showThumbs?: boolean
    autoPlay?: boolean
    autoPlayTime?: number
    siteLoading?: boolean | null
    showCaption?: boolean
    disableScroll?: boolean
    lengthToLoadMore?: number
    closable?: boolean
    closeText?: string
    previousText?: string
    nextText?: string
    previousThumbText?: string
    nextThumbText?: string
  }
  export function nextImage(): void;
  export function previousImage(): void;
  export function closeLightBox(): void;
  export function showImage(index: number): void;
}
```
