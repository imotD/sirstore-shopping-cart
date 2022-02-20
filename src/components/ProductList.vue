<template>
  <v-row>
    <v-col v-for="(product, i) in products" :key="i" cols="4">
      <v-card>
        <v-img
          height="150"
          src="https://cdn.vuetifyjs.com/images/cards/cooking.png"
        ></v-img>

        <v-card-title>{{ product.title }}</v-card-title>

        <v-card-text>
          <v-row align="center" class="mx-0">
            <v-rating
              :value="4.5"
              color="amber"
              dense
              half-increments
              readonly
              size="14"
            ></v-rating>

            <div class="grey--text ms-4">4.5 (413)</div>
          </v-row>
          <br />

          <div>
            Small plates, salads & sandwiches - an intimate setting with
          </div>
        </v-card-text>

        <v-divider class="mx-4"></v-divider>
        <v-card-actions>
          <div class="font-weight-medium">$ {{ product.price }}</div>
          <v-spacer></v-spacer>
          <v-btn color="orange lighten-2" dark @click="addToCart(product)">
            Add to cart
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
import { mapGetters, mapActions } from "vuex";

export default {
  name: "ProductList",
  data() {
    return {};
  },
  mounted() {
    this.getProducts();
  },
  computed: {
    ...mapGetters(["products"]),
  },
  methods: {
    ...mapActions(["getProducts", "addToCart"]),
  },
};
</script>

<style lang="scss" scoped>
</style>