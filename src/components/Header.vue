<script setup lang="ts">
import { ref } from "vue";

const SidebarInfos = ref([
  {
    id: 1,
    title: "Mon compte",
    value: "compte",
    avatar: "mdi mdi-account-circle",
  },
  {
    id: 2,
    title: "Parametres",
    value: "parameters",
    avatar: "mdi mdi-cog",
  },
  {
    id: 3,
    title: "FAQ Aide",
    value: "faq",
    avatar: "mdi mdi-help",
  },
]);
</script>

<template>
  <v-app-bar app color="primary" class="px-10" dark>
    <router-link :to="{ name: 'Home' }">
      <strong>ATLAS V2</strong>
    </router-link>
    <p>Milli Auction House | Beaune</p>

    <v-spacer></v-spacer>

    <router-link :to="{ name: 'Search' }" :style="{ color: 'white' }">
      <v-btn>Rechercher</v-btn>
      <v-icon size="small">mdi mdi-magnify</v-icon>
    </router-link>
  </v-app-bar>

  <v-card>
    <v-navigation-drawer expand-on-hover rail theme="dark">
      <v-list>
        <v-list-item
          prepend-avatar="/public/images.png"
          title="Milli Auction House"
          subtitle="auction_m@gmailcom"
        ></v-list-item>
      </v-list>

      <v-divider></v-divider>

      <v-list density="compact" nav>
        <v-list-item
          v-for="el in SidebarInfos"
          :key="el.id"
          :prepend-icon="el.avatar"
          :title="el.title"
          :value="el.value"
          size="small"
        ></v-list-item>
      </v-list>
    </v-navigation-drawer>
  </v-card>
</template>

<style>
a {
  text-decoration: none;
  color: white;
  padding-right: 13px;
}
</style>
