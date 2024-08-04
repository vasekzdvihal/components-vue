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

const inputName = computed(() => {
  return `input-${Math.random().toString(36).substring(7)}`;
});
</script>

<template>
  <div class="v-input-group">
    <label :for="inputName">{{ label }}</label>
    <input :class="classes" :name="inputName" :aria-label="label" type="number" :value="modelValue" @input="onInput" />
  </div>
</template>
