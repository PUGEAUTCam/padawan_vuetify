<script setup lang="ts">
import { ref } from "vue";

const accountInfos = ref([
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
const salesInfos = ref([
  {
    id: 1,
    title: "Ventes Live & Salle",
    value: "compte",
    avatar: "mdi mdi-gavel",
  },
  {
    id: 2,
    title: "Ventes Online",
    value: "parameters",
    avatar: "mdi mdi-web",
  },
  {
    id: 3,
    title: "Base Adjudications",
    value: "faq",
    avatar: "mdi mdi-currency-usd",
  },
  {
    id: 3,
    title: "Statistiques",
    value: "faq",
    avatar: "mdi mdi-chart-line",
  },
  {
    id: 3,
    title: "Journees d'expertises",
    value: "faq",
    avatar: "mdi mdi-calendar-blank-outline",
  },
  {
    id: 3,
    title: "TEMIS",
    value: "faq",
    avatar: "mdi mdi-alpha-t-box-outline",
  },
]);
</script>

<template>
  <v-app-bar app color="primary" class="px-10" dark>
    <router-link :to="{ name: 'Home' }">
      <strong>ATLAS V2</strong>
    </router-link>
    <p>Maison de ventes Milie | Beaune</p>
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
          title="Milie Auction House"
          subtitle="auction_m@gmailcom"
        ></v-list-item>
      </v-list>

      <v-divider></v-divider>
      <v-list density="compact" nav>
        <v-list-item
          v-for="el in salesInfos"
          :key="el.id"
          :prepend-icon="el.avatar"
          :title="el.title"
          :value="el.value"
        ></v-list-item>
      </v-list>
      <v-divider></v-divider>

      <template v-slot:append>
        <v-divider></v-divider>
        <v-list density="compact" nav>
          <v-list-item
            v-for="el in accountInfos"
            :key="el.id"
            :prepend-icon="el.avatar"
            :title="el.title"
            :value="el.value"
          ></v-list-item>
        </v-list>

        <v-divider></v-divider>
        <v-list density="compact" nav>
          <v-list-item prepend-icon="mdi mdi-exit-run">
            <v-btn block> Logout </v-btn>
          </v-list-item>
        </v-list>
      </template>
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
