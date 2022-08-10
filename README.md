# vue3-pagination

Library to use pagination for vue3

## Installation
To install the latest version:
```
npm install --save vue3-pagination
```

Import to your components
```javascript
import Vue3Pagination from "vue3-otp";
```

Example:
```javascript
<template>
    <vue3-pagination
      @change="handleChange"
    />
</template>
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

