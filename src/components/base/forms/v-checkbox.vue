<script setup lang="ts">
import { computed } from "vue";

const emit = defineEmits(['update:modelValue']);

defineProps({
  label: {
    type: String,
    default: '',
  },
  modelValue: {
    type: Boolean,
    default: false,
  }
});

function onInput(event: Event) {
  const target = event.target as HTMLInputElement;
  emit('update:modelValue', target.value);
}

const classes = computed(() => {
  const result = ['v-checkbox'];
  result.push('focusable');
  return result.join(' ');
})

const inputName = computed(() => {
  return `checkbox-${Math.random().toString(36).substring(7)}`;
});
</script>

<template>
  <div class="v-checkbox-group">
    <input :class="classes" type="checkbox" :name="inputName" @input="onInput">
    <label :for="inputName">{{ label }}</label>
  </div>
</template>
