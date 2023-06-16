<template>
  <div id="app">
    <NavbarC />
    <ListadoC :items="listado" />
    <!-- <LoginC /> -->
    <CarritoC />
    <FooterC />
  </div>
</template>

<script>
import NavbarC from "./components/NavbarC.vue";
import ListadoC from "./components/ListadoC.vue";
import CarritoC from "./components/CarritoC.vue";
import FooterC from "./components/FooterC.vue";
// import LoginC from "./components/LoginC.vue";

import items from "@/assets/json/items.json";

export default {
  name: "App",
  components: {
    NavbarC,
    ListadoC,
    CarritoC,
    FooterC,
    // LoginC,
  },
  data() {
    return {
      listado: items,
    };
  },
};
</script>

<style></style>
