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
  </div>
</template>
