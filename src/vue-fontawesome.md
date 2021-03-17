# `vue-fontawesome`

- Install [@fortawesome/fontawesome-svg-core](https://www.npmjs.com/package/@fortawesome/fontawesome-svg-core) package.
- Install [@fortawesome/free-solid-svg-icons](https://www.npmjs.com/package/@fortawesome/free-solid-svg-icons) package.
- Install [@fortawesome/vue-fontawesome](https://www.npmjs.com/package/@fortawesome/vue-fontawesome) package.

You use `@fortawesome/fontawesome-svg-core` in [Vue CLI](https://cli.vuejs.org/)

```ts
import Vue from 'vue'

import { library } from '@fortawesome/fontawesome-svg-core'

// Regular, Light, and Brands are existed
import {
  faCoffee,
  fas,
  faQuestion,
  faQuestionCircle,
  faPlus,
  faMinus,
  faCalendar,
  faAngleDown,
  faHome,
  faExclamationCircle,
  faBuilding,
  faUser,
  faKeyboard,
  faWallet,
  faMoneyBillWaveAlt,
  faPuzzlePiece,
  faTh,
  faBell,
  faUserCircle,
  faCheckCircle
} from '@fortawesome/free-solid-svg-icons'

import {
  FontAwesomeIcon,
  FontAwesomeLayers,
  FontAwesomeLayersText
} from '@fortawesome/vue-fontawesome'

library.add(faCoffee)
library.add(fas)
library.add(faQuestion)
library.add(faQuestionCircle)
library.add(faPlus)
library.add(faMinus)
library.add(faCalendar)
library.add(faAngleDown)
library.add(faHome)
library.add(faExclamationCircle)
library.add(faBuilding)
library.add(faUser)
library.add(faKeyboard)
library.add(faWallet)
library.add(faMoneyBillWaveAlt)
library.add(faPuzzlePiece)
library.add(faTh)
library.add(faBell)
library.add(faUserCircle)
library.add(faCheckCircle)

Vue.component('font-awesome-icon', FontAwesomeIcon)
// Vue.component('font-awesome-layers', FontAwesomeLayers)
// Vue.component('font-awesome-layers-text', FontAwesomeLayersText)
```

Use `font-awesome-icon` tag

```html
<!-- use `font-awesome-icon` tag -->
<font-awesome-icon icon="check-circle" />
```
