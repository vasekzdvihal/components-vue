<script setup lang="ts">
import VButton from "./components/base/v-button.vue";
import { Variant } from "./common/VariantEnum.ts";
</script>

<template>
  <div class="display-container">
    <v-button>primary</v-button>
    <v-button :variant="Variant.Secondary">secondary</v-button>
    <v-button :variant="Variant.Success">success</v-button>
    <v-button :variant="Variant.Danger">danger</v-button>
    <v-button :variant="Variant.Warning">warning</v-button>
    <v-button :variant="Variant.Info">info</v-button>
    <v-button :variant="Variant.Light">light</v-button>
    <v-button :variant="Variant.Dark">dark</v-button>
  </div>

  <div class="display-container">
    <v-button outline>primary</v-button>
    <v-button :variant="Variant.Secondary" outline>secondary</v-button>
    <v-button :variant="Variant.Success" outline>success</v-button>
    <v-button :variant="Variant.Danger" outline>danger</v-button>
    <v-button :variant="Variant.Warning" outline>warning</v-button>
    <v-button :variant="Variant.Info" outline>info</v-button>
    <v-button :variant="Variant.Light" outline>light</v-button>
    <v-button :variant="Variant.Dark" outline>dark</v-button>
  </div>
</template>

<style lang="scss">
.display-container {
  display: flex;
  justify-content: center;
  gap: 1em;
  margin-top: 2em;
}
</style>
