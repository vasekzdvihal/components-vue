<script setup lang="ts">
import { computed } from "vue";

const props = defineProps({
  name: {
    type: String,
    required: true,
  },
  size: {
    type: String,
    default: "24px",
  },
});

const style = computed(() => {
  return {
    fontSize: props.size,
  };
});
</script>

<template>
  <span class="material-symbols-outlined" :style="style">{{ name }}</span>
</template>
