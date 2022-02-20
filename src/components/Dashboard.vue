<template>
  <div class="dashboard">
    <div class="mb-10">
      <h3>
        <v-icon large color="orange darken-4">mdi-emoticon-kiss-outline</v-icon>
        Hi, welcome to Sirstore !
      </h3>
      <p class="text--secondary">a place where you find what you want...</p>
    </div>
    <v-row class="mb-5">
      <v-col cols="8">
        <ProductList />
      </v-col>
      <v-col cols="4">
        <Cart />
      </v-col>
    </v-row>
  </div>
</template>

<script>
import Cart from "@/components/Cart.vue";
import ProductList from "@/components/ProductList.vue";

export default {
  name: "Dashboard",
  components: {
    Cart,
    ProductList,
  },
  data() {
    return {};
  },
};
</script>

