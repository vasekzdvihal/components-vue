<script setup lang="ts">
import VButton from "./components/base/v-button.vue";
import { Variant } from "./common/VariantEnum.ts";
import VTag from "./components/base/v-tag.vue";
import VIcon from "./components/base/v-icon.vue";
import VInput from "./components/base/v-input.vue";
import { ref } from "vue";

const modelValue = ref("");
</script>

<template>
  <h3>v-button</h3>
  <div class="display-container">
    <v-button :variant="Variant.Primary" label="Primary" icon="home" />
    <v-button :variant="Variant.Secondary" label="Secondary" icon="home" />
    <v-button :variant="Variant.Success" label="Success" icon="home" />
    <v-button :variant="Variant.Danger" label="Danger" icon="home" />
    <v-button :variant="Variant.Warning" label="Warning" icon="home" />
    <v-button :variant="Variant.Info" label="Info" icon="home" />
  </div>

  <div class="display-container">
    <v-button :variant="Variant.Primary" outline label="Primary" icon="home" />
    <v-button :variant="Variant.Secondary" outline label="Secondary" icon="home" />
    <v-button :variant="Variant.Success" outline label="Success" icon="home" />
    <v-button :variant="Variant.Danger" outline label="Danger" icon="home" />
    <v-button :variant="Variant.Warning" outline label="Warning" icon="home" />
    <v-button :variant="Variant.Info" outline label="Info" icon="home" />
  </div>

  <h3>v-tag</h3>
  <div class="display-container">
    <v-tag>primary</v-tag>
    <v-tag :variant="Variant.Secondary">secondary</v-tag>
    <v-tag :variant="Variant.Success">success</v-tag>
    <v-tag :variant="Variant.Danger">danger</v-tag>
    <v-tag :variant="Variant.Warning">warning</v-tag>
    <v-tag :variant="Variant.Info">info</v-tag>
  </div>

  <h3>v-icon</h3>
  <div class="display-container">
    <v-icon name="home"></v-icon>
    <v-icon name="settings" size="2rem"></v-icon>
    <v-icon name="account_circle" size="40px"></v-icon>
    <v-icon name="notifications" size="2rem"></v-icon>
    <v-icon name="logout"></v-icon>
  </div>

  <h3>v-input</h3>
  <h4>Model value: {{ modelValue }}</h4>
  <v-input v-model="modelValue" />
</template>

<style lang="scss">
.display-container {
  display: flex;
  justify-content: center;
  gap: 1em;
  margin-top: 2em;
}
</style>
