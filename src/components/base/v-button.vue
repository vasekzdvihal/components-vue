<script setup lang="ts">
import { computed, defineProps, PropType } from 'vue';
import { Variant } from "../../common/VariantEnum.ts";
import VIcon from "./v-icon.vue";

const props = defineProps({
  label: {
    type: String,
    default: '',
  },
  icon: {
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
  flat: {
    type: Boolean,
    default: false,
  },
});

const classes = computed(() => {
  const result = ['v-button'];

  if (props.outline) result.push(`v-button--${props.variant}--outline`);
  if (props.flat) result.push(`v-button--flat`);
  if (!props.outline && !props.flat) result.push(`v-button--${props.variant}`);

  result.push('focusable');

  return result.join(' ');
})
</script>

<template>
  <button :class="classes" :aria-label="label">
    <template v-if="!$slots.default">
      <slot name="before" />
      <v-icon v-if="icon" :name="icon" />
      <span>{{ label }}</span>
      <slot name="after" />
    </template>
    <slot />
  </button>
</template>

<style lang="scss">
@use "src/style/variables" as variables;
@use "../../style/mixins" as mixins;
@use "../../style/typography";

.v-button {
  @extend .text-bold;
  padding: 15px 32px;
  text-align: center;
  text-decoration: none;
  display: inline-flex;
  justify-content: center;
  align-items: center;
  gap: 1rem;
  font-size: 16px;
  margin: 4px 2px;
  cursor: pointer;
  transition: all 0.3s;
}

.v-button--primary {
  @include mixins.solid(variables.$primary-color, variables.$white-color, variables.$border-radius, variables.$transparent-color);
  @include mixins.solid-hover(variables.$primary-color, variables.$transparent-color);
}
.v-button--secondary {
  @include mixins.solid(variables.$secondary-color, variables.$white-color, variables.$border-radius, variables.$transparent-color);
  @include mixins.solid-hover(variables.$secondary-color, variables.$transparent-color);
}
.v-button--success {
  @include mixins.solid(variables.$success-color, variables.$white-color, variables.$border-radius, variables.$transparent-color);
  @include mixins.solid-hover(variables.$success-color, variables.$transparent-color);
}
.v-button--danger {
  @include mixins.solid(variables.$danger-color, variables.$white-color, variables.$border-radius, variables.$transparent-color);
  @include mixins.solid-hover(variables.$danger-color, variables.$transparent-color);
}
.v-button--warning {
  @include mixins.solid(variables.$warning-color, variables.$white-color, variables.$border-radius, variables.$transparent-color);
  @include mixins.solid-hover(variables.$warning-color, variables.$transparent-color);
}
.v-button--info {
  @include mixins.solid(variables.$info-color, variables.$white-color, variables.$border-radius, variables.$transparent-color);
  @include mixins.solid-hover(variables.$info-color, variables.$transparent-color);
}

.v-button--primary--outline {
  @include mixins.outline(variables.$primary-color, variables.$border-radius);
  @include mixins.outline-hover(variables.$primary-color, variables.$white-color);
}
.v-button--secondary--outline {
  @include mixins.outline(variables.$secondary-color, variables.$border-radius);
  @include mixins.outline-hover(variables.$secondary-color, variables.$white-color);
}
.v-button--success--outline {
  @include mixins.outline(variables.$success-color, variables.$border-radius);
  @include mixins.outline-hover(variables.$success-color, variables.$white-color);
}
.v-button--danger--outline {
  @include mixins.outline(variables.$danger-color, variables.$border-radius);
  @include mixins.outline-hover(variables.$danger-color, variables.$white-color);
}
.v-button--warning--outline {
  @include mixins.outline(variables.$warning-color, variables.$border-radius);
  @include mixins.outline-hover(variables.$warning-color, variables.$white-color);
}
.v-button--info--outline {
  @include mixins.outline(variables.$info-color, variables.$border-radius);
  @include mixins.outline-hover(variables.$info-color, variables.$white-color);
}
</style>
