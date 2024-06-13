<script setup lang="ts">
import { defineProps } from 'vue';
import { Variant } from '../../common/VariantEnum';

defineProps({
  label: {
    type: String,
    default: '',
  },
  variant: {
    type: Variant,
    default: Variant.Primary,
  }
})
</script>

<template>
  <button class="v-button" :class="`v-button--${variant}`">
    <slot></slot>
  </button>
</template>

<style lang="scss">
.v-button {

  padding: 15px 32px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  margin: 4px 2px;
  cursor: pointer;
  transition: all 0.3s;
}

.v-button--primary {
  background-color: #a242b8;
  color: white;
  border-radius: 8px;
  border: 1px solid transparent;
}

.v-button--secondary {
  background-color: #35495e;
  color: white;
  border-radius: 8px;
  border: 1px solid transparent;
}

.v-button--success {
  background-color: #42b883;
  color: white;
  border-radius: 8px;
  border: 1px solid transparent;
}
.v-button--danger {
  background-color: #f85032;
  color: white;
  border-radius: 8px;
  border: 1px solid transparent;
}
.v-button--warning {
  background-color: #ffc107;
  color: white;
  border-radius: 8px;
  border: 1px solid transparent;
}
.v-button--info {
  background-color: #17a2b8;
  color: white;
  border-radius: 8px;
  border: 1px solid transparent;
}
.v-button--light {
  background-color: #f8f9fa;
  color: black;
  border-radius: 8px;
  border: 1px solid transparent;
}
.v-button--dark {
  background-color: #343a40;
  color: white;
  border-radius: 8px;
  border: 1px solid transparent;
}
</style>
