<template>
  <div>
    <b-sidebar id="sidebar-cart" title="" right shadow>
      <div v-if="quantity == 0" class="px-3 py-2">
        <p>No hay items en su carrito</p>
      </div>
      <div v-else>
        <b-card
          v-for="(item, i) in items"
          :key="i"
          no-body
          class="overflow-hidden"
          style="max-width: 540px"
        >
          <b-row no-gutters>
            <b-col md="6">
              <b-card-img :src="item.img" class="rounded-0"></b-card-img>
            </b-col>
            <b-col md="6">
              <b-card-body :title="item.name">
                <b-card-text>
                  <b-button-group class="float-center">
                    <b-button v-on:click="subtract(item)">-</b-button>
                    <b-button disabled>{{ item.q }}</b-button>
                    <b-button v-on:click="add(item)">+</b-button>
                  </b-button-group>
                </b-card-text>
              </b-card-body>
            </b-col>
          </b-row>
        </b-card>
      </div>

      <template #footer>
        <div class="d-flex bg-dark text-light align-items-center px-3 py-2">
          <strong class="mr-auto">Total: </strong>
          {{ totalPrice | toPrice }}

          <b-button @click="buy" id="buy-btn">CheckOut</b-button>
        </div>
      </template>
    </b-sidebar>
  </div>
</template>

<script>
import FiltersC from "./FiltersC.vue";

export default {
  name: "CarritoC",
  components: {},
  mixins: [FiltersC],
  data() {
    return {
      items: [
        {
          name: "Prod1",
          img: "",
          price: 10,
          q: 1,
        }
      ],
      quantity: 1,
      totalPrice: 10,
    };
  },
  methods: {
    add(item) {
      item.q++;
    },
    subtract(item) {
      item.q == 0 ? (item.q = 0) : item.q--;
    },
    buy() {
      console.log("Compra");
    },
  },
};
</script>

<style scoped>
.card-title {
  font-size: 1rem;
}

button {
  font-size: x-small;
}

#buy-btn {
  margin-left: 2rem;
  font-size: small;
}
</style>
