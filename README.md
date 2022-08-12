# vue3-paginator

Library to use pagination for vue3

![Gifphy](https://media.giphy.com/media/22vg60iQbzbFt2hXMg/giphy.gif)

## Installation
To install the latest version:
```
npm install --save vue3-paginator
```

Import to your components
```javascript
import Vue3Paginator from "vue3-paginator";
```

Example:
```javascript
<template>
    <vue3-paginator
      @change="handleChange"
    />
</template>

<script lang="ts">
import Vue3Paginator from '@/vue3-paginator.vue';

export default {
  components: {
    Vue3Paginator
  },
  methods: {
    handleChange(page: string) {
      console.log(`Page value is ${page}`)
    },
  },
};
</script>
```
## Props
<table>
  <tr>
    <th>Name</th>
    <th>Type</th>
    <th>Required</th>
    <th>Default</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>currentPage</td>
    <td>string</td>
    <td>false</td>
    <td>1</td>
    <td>Current active page</td>
  </tr>
  <tr>
    <td>perPage</td>
    <td>string</td>
    <td>false</td>
    <td>10</td>
    <td>Items count for one page</td>
  </tr>
  <tr>
    <td>total</td>
    <td>number</td>
    <td>false</td>
    <td>100</td>
    <td>Total count of items</td>
  </tr>
  </tr>
</table>

## Events
<table>
  <tr>
    <th>Name</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>change</td>
    <td>Handle click</td>
  </tr>
</table>

Slots:
```javascript
<template>
  <vue3-paginator
    @change="handleChange"
    currentPage="2"
    perPage="5"
    :total="200"
  >
    <template v-slot:prev-button>
      <div>prev</div>
    </template>
    <template v-slot:next-button>
      <div>next</div>
    </template>
  </vue3-paginator>
</template>
```

## css default variables
<table>
    <tr>
        <th>Name</th>
        <th>Value</th>
    </tr>
    <tr>
        <th>--primary-color</th>
        <th>#42b984</th>
    </tr>
    <tr>
        <th>--pg-item-width</th>
        <th>40px</th>
    </tr>
    <tr>
        <th>--pg-item-height</th>
        <th>40px</th>
    </tr>
    <tr>
        <th>--pg-item-border-radius</th>
        <th>50%</th>
    </tr>
    <tr>
        <th>--pg-item-distance</th>
        <th>5px</th>
    </tr>
</table>
