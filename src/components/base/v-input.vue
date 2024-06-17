<script setup lang="ts">
import { computed } from "vue";

const emit = defineEmits(['update:modelValue']);
defineProps({
  modelValue: {
    type: String,
    default: '',
  },
});

function onInput(event: Event) {
  const target = event.target as HTMLInputElement;
  emit('update:modelValue', target.value);
}

const classes = computed(() => {
  const result = ['v-input'];

  result.push('focusable');

  return result.join(' ');
})
</script>

<template>
  <input :class="classes" type="text" :value="modelValue" @input="onInput">
</template>

<style scoped lang="scss">
@use "src/style/variables" as variables;

.v-input {
  padding: 10px;
  border: 1px solid variables.$primary-color;
  border-radius: variables.$border-radius;
  background: variables.$dark-color;
  font-size: 16px;
  font-weight: 500;
  letter-spacing: 0.5px;
  width: 100%;
}
</style>
