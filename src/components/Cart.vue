<template>
  <div>
    <v-alert v-if="!cart.length" type="info"> No Product in cart! </v-alert>
    <v-alert v-if="orderLoading" type="success">
      Order Successfully placed!
      <v-btn @click="() => (orderLoading = false)" small rounded icon>
        <v-icon>mdi-delete</v-icon>
      </v-btn>
    </v-alert>
    <v-card
      class="mx-auto"
      max-width="344"
      outlined
      v-for="item in cart"
      :key="item.id"
    >
      <v-list-item three-line>
        <v-list-item-content>
          <v-list-item-title class="text-h5 mb-1">
            {{ item.title }}
          </v-list-item-title>
          <v-list-item-subtitle>
            Greyhound divisely hello coldly fonwderfully
          </v-list-item-subtitle>
        </v-list-item-content>

        <v-list-item-avatar tile size="80" color="grey">
          <v-img
            src="https://cdn.vuetifyjs.com/images/cards/cooking.png"
          ></v-img>
        </v-list-item-avatar>
      </v-list-item>

      <v-card-actions>
        <v-btn small outlined rounded icon @click="reduceQty(item.id)">
          <v-icon>mdi-minus</v-icon>
        </v-btn>
        <div class="mx-3">x {{ item.qty }}</div>
        <v-btn small outlined rounded icon @click="addQty(item.id)">
          <v-icon>mdi-plus</v-icon>
        </v-btn>
        <v-spacer></v-spacer>
        <v-btn small rounded icon @click="removeItem(item.id)">
          <v-icon>mdi-delete</v-icon>
        </v-btn>
      </v-card-actions>
    </v-card>
    <v-btn block color="warning">Checkout($ {{ totalPrice }})</v-btn>
  </div>
</template>

<script>
import { mapActions, mapGetters } from "vuex";
export default {
  name: "Cart",
  data() {
    return {
      isLoading: false,
      orderLoading: false,
    };
  },
  computed: {
    ...mapGetters(["cart"]),
    totalPrice() {
      return this.cart.reduce((a, b) => a + b.qty * b.price, 0);
    },
  },
  methods: {
    ...mapActions(["addQty", "reduceQty", "removeItem", "emptyCart"]),
    placeOrder() {
      this.isLoading = true;
      setTimeout(() => {
        this.orderLoading = true;
        this.isLoading = false;
        this.emptyCart();
      }, 1000);
    },
  },
};
</script>

<style lang="scss" scoped>
</style>