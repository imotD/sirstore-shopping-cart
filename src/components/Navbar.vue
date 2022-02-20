<template>
  <div>
    <v-app-bar fixed dark elevate-on-scroll>
      <v-toolbar flat>
        <v-toolbar-title class="font-weight-bold"> Sirstore </v-toolbar-title>

        <v-spacer></v-spacer>
        <v-badge
          v-if="totalQty"
          bordered
          overlap
          bottom
          color="orange"
          :content="totalQty"
        >
          <v-btn icon fab flat>
            <v-icon> mdi-cart-variant </v-icon>
          </v-btn>
        </v-badge>

        <v-btn v-else icon fab flat>
          <v-icon> mdi-cart-variant </v-icon>
        </v-btn>
      </v-toolbar>
    </v-app-bar>
  </div>
</template>

<script>
import { mapGetters } from "vuex";
export default {
  name: "Navbar",
  data() {
    return {};
  },
  computed: {
    ...mapGetters(["cart"]),
    totalQty() {
      return this.cart.reduce((a, b) => a + b.qty, 0);
    },
  },
};
</script>

<style lang="scss" scoped>
</style>