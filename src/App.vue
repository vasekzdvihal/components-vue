<script setup lang="ts">
import VButton from "./components/base/v-button.vue";
import { Variant } from "./common/VariantEnum.ts";
import VTag from "./components/base/v-tag.vue";
import VIcon from "./components/base/v-icon.vue";
</script>

<template>
  <h3>v-button</h3>
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

  <h3>v-tag</h3>
  <div class="display-container">
    <v-tag>primary</v-tag>
    <v-tag :variant="Variant.Secondary">secondary</v-tag>
    <v-tag :variant="Variant.Success">success</v-tag>
    <v-tag :variant="Variant.Danger">danger</v-tag>
    <v-tag :variant="Variant.Warning">warning</v-tag>
    <v-tag :variant="Variant.Info">info</v-tag>
    <v-tag :variant="Variant.Light">light</v-tag>
    <v-tag :variant="Variant.Dark">dark</v-tag>
  </div>

  <h3>v-icon</h3>
  <div class="display-container">
    <v-icon name="home"></v-icon>
    <v-icon name="settings" size="2rem"></v-icon>
    <v-icon name="account_circle" size="40px"></v-icon>
    <v-icon name="notifications" size="2rem"></v-icon>
    <v-icon name="logout"></v-icon>
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
