# nuxt-compress

A simple static asset compression module for Nuxt that runs Gzip and
Brotli compression.

## Getting Started

1. Install the module

   ```console
   npm install nuxt-compress
   ```

   OR

   ```console
   yarn add nuxt-compress
   ```

2. Add the module to your `nuxt.config.js`

   ```js
   module.exports = {
     modules: ["nuxt-compress"]
   };
   ```

## Configuration

This module provides a simple interface to include
[brotli-webpack-plugin](https://github.com/mynameiswhm/brotli-webpack-plugin)
and
[compression-webpack-plugin](https://github.com/webpack-contrib/compression-webpack-plugin)
and uses the same configuration options, which can be supplied as a
second argument to the entry in `"modules"` in your `nuxt.config.js`, or as
a distinct entry with the key `"nuxt-compress"`. See the
[Nuxt Modules guide](https://nuxtjs.org/guide/modules/) for more information.

For example:

```js
module.exports = {
  modules: [
    [
      "nuxt-compress",
      {
        gzip: {
          cache: true
        },
        brotli: {
          threshold: 10240
        }
      }
    ]
  ]
};
```

OR

```js
module.exports = {
  modules: ["nuxt-compress"],
  "nuxt-compress": {
    gzip: {
      cache: true
    },
    brotli: {
      threshold: 10240
    }
  }
};
```