---
title: Portable text
description: 'Access text, images, and other media with Nuxt and the Sanity headless CMS.'
category: Helpers
position: 10
version: 0.11
---

## Global helper

This module defines a global `<SanityContent>` component that can turn portable text into HTML. It is a lightweight functional component without an instance. It has been designed to be functionally equivalent to [sanity-blocks-vue-component](https://github.com/rdunk/sanity-blocks-vue-component) while addressing some of its shortfalls.

### Example

```vue
<template>
  <SanityContent :blocks="content" />
</template>
```

## Local import

You may wish to import `SanityContent` only in the components that need it if you have disabled the global `contentHelper` option. Note that you will need to provide your `projectId` (and `dataset` if not `production`):

### Example

```vue
<template>
  <SanityContent :blocks="content" />
</template>

<script>
import { SanityContent } from '@nuxtjs/sanity/dist/sanity-content'

export default {
  components: { SanityContent },
}
</script>
```

## Other resources

- [sanity-blocks-vue-component](https://github.com/rdunk/sanity-blocks-vue-component)
