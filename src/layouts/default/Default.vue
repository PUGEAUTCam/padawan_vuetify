<template>
  <v-app>
    <default-bar />

    <default-view />
  </v-app>
</template>

<script lang="ts" setup>
import DefaultBar from "./AppBar.vue";
import DefaultView from "./View.vue";
</script>

<style>
header {
  padding: 0px;
}
main {
  margin: 0 auto;
  max-width: 1280px;
}
</style>
