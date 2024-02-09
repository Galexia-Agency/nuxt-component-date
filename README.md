# Galexia Nuxt Component Date

## Install

### Pre-Requisites

We assume you have a Nuxt project.

### You can now install this package

```bash
yarn add https://github.com/Galexia-Agency/nuxt-component-date
```

```js
// plugins/galexia/nuxt-components/date.js
import Vue from 'vue'
import Galexia_NuxtComponent_Date from 'nuxt-component-date/index.vue'

Vue.component('GalexiaDate', Galexia_NuxtComponent_Date)
```

```js
// nuxt.config.js
...
plugins: [
  '~plugins/galexia/nuxt-components/date.js'
],
...
```

### And use it like so

```js
// pages/index.js
<GalexiaDate
  class="post__date"
  :date="post.date"
  day-text-color="#ffffff"
  day-background-color="#000000"
  month-year-text-color="#ffffff"
  month-year-background-color="#333333"
/>
```
