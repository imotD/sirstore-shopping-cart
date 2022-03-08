<template>
  <div class="dashboard my-16">
    <v-row>
      <v-col cols="4">
        <v-card to="/product/12" class="rounded-lg">
          <v-img
            src="../assets/image/image-product-1.jpg"
            height="400"
            max-height="400"
          ></v-img>
        </v-card>
      </v-col>
    </v-row>
    <!-- <v-row class="mb-5">
      <v-col cols="8">
        <ProductList />
      </v-col>
      <v-col cols="4">
        <Cart />
      </v-col>
    </v-row> -->
  </div>
</template>

<script>
// import Cart from "@/components/Cart.vue";
// import ProductList from "@/components/ProductList.vue";

export default {
  name: "Dashboard",
  components: {
    // Cart,
    // ProductList,
  },
  data() {
    return {};
  },
};
</script>

