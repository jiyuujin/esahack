# `vue-datetimerange-picker`

Install [vue-datetimerange-picker](https://www.npmjs.com/package/vue-datetimerange-picker) package

```bash
npm i vue-datetimerange-picker

yarn add vue-datetimerange-picker
```

You can use as general CSS frameworks

```js
import Vue from 'vue'
import { CoreUI } from 'vue-datetimerange-picker'
import 'vue-datetimerange-picker/dist/vue-range-picker.css'

Vue.use(CoreUI)
```

#### Props

```html
<v-range-picker
    ref="range-picker"
    :show-dropdown="showDropdown"
    :auto-apply="autoApply"
    :linked-calendars="linkedCalendars"
    :date-range="dateRange"
    :opens="opens"
    :date-format="dateFormat"
    @update="updateValues"
    @toggle="checkOpen"
>
    <div slot="input" slot-scope="picker" style="min-width: 350px;">
        {{ picker.startDate }} - {{ picker.endDate }}
    </div>
</v-range-picker>
```

`dateRange` is required, but set custom ranges in `ranges`

| # | Type | Default |
|:---|:---|:---|
| minDate | `Date` | `` |
| maxDate | `Date` | `` |
| linkedCalendars | `Boolean` | `true` |
| showDropdown | `Boolean` | `false` |
| dateRange | `Object` | `` |
| ranges | `Object` | `` |
| localeData | `Object` | `` |
| opens | `String` | `center` ( `left` / `right` ) |
| dateFormat | `Boolean` | `true` |
| timePicker | `Boolean` | `false` |
| timePickerIncrement | `Number` | `5` |
| timePicker24Hour | `Boolean` | `true` |
| timePickerSeconds | `Boolean` | `false` |
