<template>
  <div id="app">
    <NavbarC />
    <ListadoC :items="listado" />
    <CarritoC />
    <FooterC />
  </div>
</template>

<script>
import NavbarC from "./components/NavbarC.vue";
import ListadoC from "./components/ListadoC.vue";
import CarritoC from "./components/CarritoC.vue";
import FooterC from "./components/FooterC.vue";

import items from "@/assets/json/items.json";

export default {
  name: "App",
  components: {
    NavbarC,
    ListadoC,
    CarritoC,
    FooterC,
  },
  data() {
    return {
      listado: items,
    };
  },
};
</script>

<style></style>
