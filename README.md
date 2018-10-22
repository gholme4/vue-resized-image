### A Vue JS component that dynamically resizes, crops, and displays images

## Table of contents

- [Installation](#installation)
- [Usage](#usage)
- [Example](#example)

# Installation

```
npm install --save vue-resized-image
```

## Default import

Install all the components:

```javascript
import Vue from 'vue'
import { VueResizedImage } from 'vue-resized-image'

Vue.use(VueResizedImage)
```

Use specific components:

```javascript
import Vue from 'vue'
import { VueResizedImage } from 'vue-resized-image'

Vue.component('resized-image', VueResizedImage)
```


## Distribution import

Install all the components:

```javascript
import VueResizedImage from 'vue-resized-image/dist/vue-resized-image.common'

Vue.use(VueResizedImage)
```

Use specific components:

```javascript
import { VueResizedImage } from 'vue-resized-image/dist/vue-resized-image.common'

Vue.component('resized-image', VueResizedImage)
```

## Browser

```html

<script src="vue.js"></script>
<script src="vue-resized-image/dist/vue-resized-image.browser.js"></script>
```

The plugin should be auto-installed. If not, you can install it manually with the instructions below.

Install all the components:

```javascript
Vue.use(VueResizedImage)
```

## Source import

Install all the components:

```javascript
import Vue from 'vue'
import VueResizedImage from 'vue-resized-image/src'

Vue.use(VueResizedImage)
```

**⚠️ You need to configure your bundler to compile `.vue` files.** More info [in the official documentation](https://vuejs.org/v2/guide/single-file-components.html).

# Usage

> TODO

# Example

> TODO

---

# Plugin Development

## Installation

The first time you create or clone your plugin, you need to install the default dependencies:

```
npm install
```

## Watch and compile

This will run webpack in watching mode and output the compiled files in the `dist` folder.

```
npm run dev
```

## Use it in another project

While developping, you can follow the install instructions of your plugin and link it into the project that uses it.

In the plugin folder:

```
npm link
```

In the other project folder:

```
npm link vue-resized-image
```

This will install it in the dependencies as a symlink, so that it gets any modifications made to the plugin.


## Manual build

This will build the plugin into the `dist` folder in production mode.

```
npm run build
```

---

## License

[MIT](http://opensource.org/licenses/MIT)
