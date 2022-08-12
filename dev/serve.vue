<script lang="ts">
import Vue3Paginator from '@/vue3-paginator.vue';

export default {
  name: 'ServeDev',
  components: {
    Vue3Paginator
  },
  methods: {
    handleChange(page: string) {
      console.log(`Page value is ${page}`)
    }
  },
};
</script>

<template>
  <div id="app">
    <vue3-paginator
      @change="handleChange"
    />
  </div>
</template>
