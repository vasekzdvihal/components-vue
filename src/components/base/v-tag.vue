<script setup lang="ts">
import { computed, PropType } from "vue";
import { Variant } from "../../common/VariantEnum.ts";

const props = defineProps({
  variant: {
    type: String as PropType<Variant>,
    default: Variant.Primary,
  },
})

const classes = computed(() => {
  const result = ['v-tag'];
  result.push(`v-tag--${props.variant}`);
  return result.join(' ');
});
</script>

<template>
  <div :class="classes">
    <slot></slot>
  </div>
</template>

<style scoped lang="scss">
@use "src/style/variables" as variables;
@use "../../style/mixins" as mixins;
@use "../../style/typography";

.v-tag {
  @extend .text-medium;
  padding: 5px 10px;
  border-radius: 5px;
  display: inline-block;
  font-size: 14px;
  font-weight: 500;
  letter-spacing: 0.5px;
}

.v-tag--primary {
  @include mixins.tag-solid(variables.$primary-color, variables.$white-color, variables.$border-radius);
}
.v-tag--secondary {
  @include mixins.tag-solid(variables.$secondary-color, variables.$white-color, variables.$border-radius);
}
.v-tag--success {
  @include mixins.tag-solid(variables.$success-color, variables.$white-color, variables.$border-radius);
}
.v-tag--danger {
  @include mixins.tag-solid(variables.$danger-color, variables.$white-color, variables.$border-radius);
}
.v-tag--warning {
  @include mixins.tag-solid(variables.$warning-color, variables.$white-color, variables.$border-radius);
}
.v-tag--info {
  @include mixins.tag-solid(variables.$info-color, variables.$white-color, variables.$border-radius);
}
.v-tag--light {
  @include mixins.tag-solid(variables.$light-color, variables.$dark-color, variables.$border-radius);
}
.v-tag--dark {
  @include mixins.tag-solid(variables.$dark-color, variables.$white-color, variables.$border-radius);
}
</style>
