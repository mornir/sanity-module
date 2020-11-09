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

### Props

#### `blocks`

An array of [Portable Text](https://www.sanity.io/docs/block-type) from Sanity to be rendered into HTML.

- Type: **array**

#### `serializers.types`

Specifies the functions to use for rendering content. Merged with default serializers.

- Type: **object**

#### `serializers.marks`

#### `renderContainerOnSingleChild`

When a single block is given as input, the default behavior is to not render any container. If you always want to render the container, pass `true`.

- Type: **boolean**

### Serializers

They can be defined either as a string (e.g. div) or as a Vue Component (see below for more detail). This package comes with default serializers that will work for rendering basic block content, but you may pass a serializer prop to override or extend the default serializers. The object passed will be merged with the default serializers object.

#### Blocks

#### Marks

## Local import

You may wish to import `SanityContent` only in the components that need it if you have disabled the global `contentHelper` option. Note that you will need to provide your `projectId` (and `dataset` if not `production`):

### Example

```vue
<template>
  <SanityContent :blocks="content" projectId="xxxxx" dataset="staging" />
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
