<template>
  <div>
    <b-modal id="modal-info" centered :title="item.name">
      <template #modal-header>
        <div class="w-100">
          <b-img rounded="top" :src="item.img"></b-img>
        </div>
      </template>

      <h3>{{ item.name }}</h3>
      <p class="my-4">{{ item.price | toPrice }}</p>
      <p>{{ item.desc }}</p>

      <template #modal-footer>
        <div class="w-100">
          <b-button-group class="float-left">
            <b-button v-on:click="subtract">-</b-button>
            <b-button disabled>{{ quantity }}</b-button>
            <b-button v-on:click="add">+</b-button>
          </b-button-group>

          <b-button class="float-right" v-on:click="addToCart()">
            <b-icon icon="cart-plus" class="nav-icon"></b-icon>
          </b-button>
        </div>
      </template>
    </b-modal>
  </div>
</template>

<script>
import FiltersC from "./FiltersC.vue";

export default {
  name: "InfoC",
  props: {
    item: {},
  },
  mixins: [FiltersC],
  data() {
    return {
      quantity: 1,
    };
  },
  methods: {
    addToCart() {
      console.log(
        `add to cart desde info: ${this.item.name}, q: ${this.quantity}`
      );
      this.$bvModal.hide("modal-info");
    },
    add() {
      this.quantity++;
    },
    subtract() {
      this.quantity == 0 ? (this.quantity = 0) : this.quantity--;
    },
  },
};
</script>

<style scoped>
img {
  width: 100%;
  max-height: 22rem;
}

.modal-header {
  padding: 0;
}

button:disabled {
  background-color: crimson;
}
</style>
