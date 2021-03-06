![alt text](assets/logo.png "Demo GIF")
# vue-farewell
> A vue directive to know when a user is leaving the page
>
> Port of [ouibounce](https://github.com/carlsednaoui/ouibounce).

[![semantic-release](https://img.shields.io/badge/%20%20%F0%9F%93%A6%F0%9F%9A%80-semantic--release-e10079.svg?style=flat-square)](https://github.com/semantic-release/semantic-release)
[![version](https://img.shields.io/npm/v/vue-farewell.svg?style=flat-square)](http://npm.im/vue-farewell)
[![downloads](https://img.shields.io/npm/dm/vue-farewell.svg?style=flat-square)](http://npm-stat.com/charts.html?package=vue-farewell&from=2018-01-16)
[![travis build](https://img.shields.io/travis/SahajR/pokemon-names-and-types.svg?style=flat-square)](https://travis-ci.org/SahajR/vue-farewell)
[![size](http://img.badgesize.io/SahajR/vue-farewell/master/dist/lib/vue-farewell.min.js?compression=gzip&style=flat-square&label=only)](dist/lib/vue-farewell.min.js)
![alt text](assets/demo.gif "Demo GIF")

## Usage
Install via npm or yarn.
```
npm install vue-farewell
or
yarn add vue-farewell
```
Install it globally
```js
import Vue from 'vue'
import { farewellDirectivePlugin } from 'vue-farewell'

Vue.use(farewellDirectivePlugin)
```
Then

```vue
<template>
  <div style="position: relative;">
    <div v-farewell="onLeave">Don't leave!</div>
  </div>
</template>

export default {
  name: 'app',
  methods: {
    onLeave () {
      console.log('Gone!')
    }
  }
}
```

## Options
You may pass options while installing the directive globally.
```js
import Vue from 'vue'
import { farewellDirectivePlugin } from 'vue-farewell'

const options = {
  cookieName: 'someCustomCookieName'
}

Vue.use(farewellDirectivePlugin, options)
```

| Option name | Type | Description |
| ------ | ------ | ------ |
| sensitivity | Number | How close the mouse needs to be to fire the exit (tolerance). The higher this value, the earlier the exit intent is identified. |
| delay | Number | Once an exit intent is recorded, the time after which the callback events should be fired. |
| cookieName | String | The key that will be used to store the cookie that logs if the user has exited once. Default: `fired_once` |
| cookieDomain | String | The cookie's domain |
| cookieExpire | Number | The number of days that mark the cookie's expiration. Default: `7 days` |
| sitewide | Boolean | Sets the scope of the cookie to site-wide |
| aggressive | Boolean | Will fire every time the user tries to leave. Default: `false` |
| elementHiddenByDefault | Boolean | Will make the attached element hidden by default. Default: `true` |
| elementDisplayStyleOnFire | String | Will make the attached element's display style from 'none' to this value once an exit is triggered. Default: `block` |


## License
```
The MIT License (MIT)

Copyright © 2018 SahajR

Permission is hereby granted, free of charge, to any person
obtaining a copy of this software and associated documentation
files (the “Software”), to deal in the Software without
restriction, including without limitation the rights to use,
copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the
Software is furnished to do so, subject to the following
conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED “AS IS”, WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES
OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND
NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT
HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY,
WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING
FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR
OTHER DEALINGS IN THE SOFTWARE.
```
