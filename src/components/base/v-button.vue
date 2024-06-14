<script setup lang="ts">
import { computed, defineProps, PropType } from 'vue';
import { Variant } from "../../common/VariantEnum.ts";

const props = defineProps({
  label: {
    type: String,
    default: '',
  },
  variant: {
    type: String as PropType<Variant>,
    default: Variant.Primary,
  },
  outline: {
    type: Boolean,
    default: false,
  },
})

const classes = computed(() => {
  const result = ['v-button'];

  if (!props.outline) {
    result.push(`v-button--${props.variant}`);
  } else {
    result.push(`v-button--${props.variant}--outline`);
  }

  return result.join(' ');
})
</script>

<template>
  <button class="v-button" :class="classes">
    <slot></slot>
  </button>
</template>

<style lang="scss">
@use "src/style/variables" as variables;
@use "../../style/mixins" as mixins;

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
  @include mixins.button-solid(variables.$primary-color, variables.$white-color, variables.$border-radius, variables.$transparent-color);
}
.v-button--secondary {
  @include mixins.button-solid(variables.$secondary-color, variables.$white-color, variables.$border-radius, variables.$transparent-color);
}
.v-button--success {
  @include mixins.button-solid(variables.$success-color, variables.$white-color, variables.$border-radius, variables.$transparent-color);
}
.v-button--danger {
  @include mixins.button-solid(variables.$danger-color, variables.$white-color, variables.$border-radius, variables.$transparent-color);
}
.v-button--warning {
  @include mixins.button-solid(variables.$warning-color, variables.$white-color, variables.$border-radius, variables.$transparent-color);
}
.v-button--info {
  @include mixins.button-solid(variables.$info-color, variables.$white-color, variables.$border-radius, variables.$transparent-color);
}
.v-button--light {
  @include mixins.button-solid(variables.$light-color, variables.$black-color, variables.$border-radius, variables.$transparent-color);
}
.v-button--dark {
  @include mixins.button-solid(variables.$dark-color, variables.$white-color, variables.$border-radius, variables.$transparent-color);
}

.v-button--primary--outline {
  @include mixins.button-outline(variables.$primary-color, variables.$border-radius);
}
.v-button--secondary--outline {
  @include mixins.button-outline(variables.$secondary-color, variables.$border-radius);
}
.v-button--success--outline {
  @include mixins.button-outline(variables.$success-color, variables.$border-radius);
}
.v-button--danger--outline {
  @include mixins.button-outline(variables.$danger-color, variables.$border-radius);
}
.v-button--warning--outline {
  @include mixins.button-outline(variables.$warning-color, variables.$border-radius);
}
.v-button--info--outline {
  @include mixins.button-outline(variables.$info-color, variables.$border-radius);
}
.v-button--light--outline {
  @include mixins.button-outline(variables.$light-color, variables.$border-radius);
}
.v-button--dark--outline {
  @include mixins.button-outline(variables.$dark-color, variables.$border-radius);
}
</style>
