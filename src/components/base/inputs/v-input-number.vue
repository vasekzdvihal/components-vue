<script setup lang="ts">
import { computed } from "vue";

const emit = defineEmits(['update:modelValue']);
defineProps({
  label: {
    type: String,
    default: '',
  },
  modelValue: {
    type: Number,
    default: 0,
  }
});

function onInput(event: Event) {
  const target = event.target as HTMLInputElement;
  emit('update:modelValue', target.value);
}

const classes = computed(() => {
  const result = ['v-input'];

  result.push('focusable');

  return result.join(' ');
});
</script>

<template>
  <div class="v-input-group">
    <label for="input">{{ label }}</label>
    <input :class="classes" type="number" :value="modelValue" @input="onInput" />
  </div>
</template>
