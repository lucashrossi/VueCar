<template>
  <div>
    <div class="cabecera"></div>
    <b-card-group columns>
      <b-card
        v-for="(item, i) in items"
        :key="i"
        :title="item.name"
        :img-src="item.img"
        img-alt="Image"
        img-top
      >
        <b-card-text>
          {{ item.price | toPrice }}
        </b-card-text>

        <b-button v-b-modal.modal-info v-on:click="showInfo(item)">
          Mas
        </b-button>
        <b-button v-on:click="addToCart(item)">
          <b-icon icon="cart-plus" class="nav-icon"></b-icon>
        </b-button>
      </b-card>
    </b-card-group>

    <InfoC :item="item" />
  </div>
</template>

<script>
import InfoC from "./InfoC.vue";
import FiltersC from "./FiltersC.vue";

export default {
  name: "ListadoC",
  components: {
    InfoC,
  },
  props: {
    items: Array,
  },
  mixins: [FiltersC],
  data() {
    return {
      item: {
        name: "",
        img: "",
        price: 0,
        desc: "",
      },
    };
  },
  methods: {
    addToCart(item) {
      console.log("add to cart: ", item.name);
    },
    showInfo(item) {
      console.log("info de: ", item.name);
      this.item = item;
    },
  },
};
</script>

<style scoped>
.cabecera {
  height: 60px;
}

.card-columns .card {
  width: 90%;
  margin-top: 2rem;
  margin-bottom: 1rem;
}

.card {
  border-radius: 45%;
}

.card-img-top {
  border-top-left-radius: 15%;
  border-top-right-radius: 15%;
  max-height: 15rem;
  max-width: 100%;
}

button {
  margin-right: 1rem;
  margin-left: 1rem;
}
</style>
