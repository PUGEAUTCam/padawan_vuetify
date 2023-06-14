<script setup lang="ts">
import { ref } from "vue";

const categoriesProperties = ref([
  {
    id: 1,
    title: "Créer une nouvelle vente",
    img: "/public/papiers-peints-theme-droit-maillet-de-juge-marteau-en-bois.jpg.jpg",
  },
  {
    id: 2,
    title: "Ventes passées / Résultats",
    img: "/public/iconeek-sales-cover_crop_w1396_h781_1396x781.jpg",
  },
  {
    id: 4,
    title: "Base d'adjudications",
    img: "/public/bourgognes.jpg",
  },
  {
    id: 5,
    title: "Journées d'expertises",
    img: "/public/07e3f5c579f74d0fe616125f4e25a8772a016f30_chaplins_cassina_lc4_chaise_lounge_main_1__31436.jpg",
  },
  {
    id: 6,
    title: "Suivi des paiements / stripe",
    img: "/public/Judith-et-Holopherne-vers-1598-1599-Galerie-nationale-dart-ancien-Rome-1.jpg",
  },
  {
    id: 7,
    title: "FAQ  Guide d'utilisation",
    img: "/public/02-une-rue-streetartisecc81e-au-mans.webp",
  },
]);
</script>

<template>
  <v-container class="pa-4 text-center">
    <h2>Mon espace Atlas</h2>

    <v-row class="fill-height" align="center" justify="center">
      <template v-for="(el, i) in categoriesProperties" :key="i">
        <v-col cols="12" md="4">
          <v-hover v-slot="{ isHovering, props }">
            <v-card
              :elevation="isHovering ? 12 : 2"
              :class="{ 'on-hover': isHovering }"
              v-bind="props"
            >
              <v-img :src="el.img" height="225px" cover> </v-img>
              <v-card-title>{{ el.title }}</v-card-title>
            </v-card>
          </v-hover>
        </v-col>
      </template>
    </v-row>
  </v-container>
</template>

<style scoped>
.v-card {
  transition: opacity 0.4s ease-in-out;
}
.v-card:not(.on-hover) {
  opacity: 0.7;
}
.show-btns {
  color: rgba(255, 255, 255, 1) !important;
}
h2 {
  margin-top: 27px;
  text-align: center;
  margin-bottom: 27px;
}
p {
  font-size: 25px;
}
</style>
