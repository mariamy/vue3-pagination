<script lang="ts">
import { defineComponent } from 'vue';
import Vue3Paginator from '@/vue3-paginator.vue';

export default defineComponent({
  name: 'ServeDev',
  components: {
    Vue3Paginator
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
    <vue3-paginator
      @change="handleChange"
    />
  </div>
</template>
