<script lang="ts">
import { defineComponent } from 'vue';
import Vue3Pagination from '@/vue3-pagination.vue';

export default defineComponent({
  name: 'ServeDev',
  components: {
    Vue3Pagination
  },
  methods: {
    handleChange(page: string) {
      console.log(`page value is ${page}`)
    }
  },
});
</script>

<template>
  <div id="app">
    <vue3-pagination
      @change="handleChange"
    />
  </div>
</template>
