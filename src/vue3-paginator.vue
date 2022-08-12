<script lang="ts">
import { defineComponent } from 'vue';

interface SampleData {
  activePage: number;
}

export default /*#__PURE__*/defineComponent({
  name: 'Vue3paginator',
  props: {
    currentPage: {
      type: [String, Number],
      default: "1"
    },
    perPage: {
      type: String,
      default: "10"
    },
    total: {
      type: Number,
      default: 100
    },
    space: {
      type: String,
      default: "..."
    }
  },
  data(): SampleData {
    return {
      activePage: parseInt(this.currentPage as string)
    };
  },
  computed: {
    pages(): any {
      const pages = [];
      const edge = 3;
      const count = Math.ceil(this.total / parseInt(this.perPage));

      for (let i = 1; i <= count; i++) {
        const _distance = Math.abs(i - this.activePage);

        if (
          i === 1 ||
          i === count ||
          _distance < edge ||
          (_distance === edge && _distance === count - 2)
        ) {
          pages.push({
            id: i,
            n: i
          });
        } else if (_distance === edge) {
          pages.push({
            id: i,
            n: this.space
          });
        }
      }
      return pages;
    }
  },
  methods: {
    setPage(page: number): void {
      if (isNaN(page) || page === Number(this.activePage)) return;
      this.activePage = page;
      this.$emit("change", page.toString());
    },
  },
  watch: {
    currentPage(newValue, oldValue) {
      if (newValue !== oldValue)
        this.activePage = parseInt(newValue as string);
    }
  }
});
</script>

<template>
  <div class="paginator-container">
    <a
      @click.prevent="setPage(activePage > 1 ? activePage - 1 : 1)"
      class="paginator-item paginator-item-prev"
      :class="{ disabled: activePage === 1 }"
    >
      <slot name="prev-button">&lsaquo;</slot>
    </a>

    <div class="paginator-items">
      <a
        v-for="p in pages"
        :key="p.id"
        class="paginator-item"
        :class="{
          active: activePage === p.n,
          disabled: p.n === space
        }"
        @click.prevent="setPage(p.n)"
        >
          {{ p.n }}
        </a>
    </div>

    <a
      @click.prevent="
        setPage(
          activePage < pages[pages.length - 1].n
            ? activePage + 1
            : pages[pages.length - 1].n
        )
      "
      class="paginator-item paginator-item-next"
      :class="{ disabled: activePage === pages[pages.length - 1].n }"
    >
      <slot name="next-button">&rsaquo;</slot>
    </a>
  </div>
</template>

<style>
:root {
  --primary-color: #42b984;
  --pg-item-width: 40px;
  --pg-item-height: 40px;
  --pg-item-border-radius: 50%;
  --pg-item-distance: 5px;
}
.paginator-container {
  display: flex;
  align-items: center;
  gap: var(--pg-item-distance);
}
.paginator-items {
  display: flex;
  gap: var(--pg-item-distance);
}
.paginator-item {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: var(--pg-item-width);
  height: var(--pg-item-height);
  border-radius: var(--pg-item-border-radius);
}
.paginator-item.active {
  background: var(--primary-color);
  color: #fff;
}
.paginator-item:not(.active):active {
  color: var(--primary-color);
} 
.paginator-item:not(.disabled) {
  cursor: pointer;
  opacity: 1;
}
.paginator-item.disabled {
  opacity: .3;
}
</style>