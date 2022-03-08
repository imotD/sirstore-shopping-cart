<template>
  <v-app-bar class="white navbar" fixed elevate-on-scroll height="85">
    <v-container class="navbar__br-b">
      <v-toolbar flat>
        <v-toolbar-title>
          <v-img src="../assets/image/logo.svg"></v-img>
        </v-toolbar-title>
        <div class="pl-10">
          <v-btn
            v-for="(menu, i) in menus"
            :key="i"
            text
            plain
            class="text-capitalize font-weight-regular"
          >
            {{ menu.title }}
          </v-btn>
        </div>
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

        <v-btn v-else icon fab>
          <v-icon> mdi-cart-variant </v-icon>
        </v-btn>

        <v-btn icon fab class="ml-5">
          <v-avatar>
            <img src="../assets/image/image-avatar.png" alt="John" />
          </v-avatar>
        </v-btn>
      </v-toolbar>
    </v-container>
  </v-app-bar>
</template>

<script>
import { mapGetters } from "vuex";
export default {
  name: "Navbar",
  data() {
    return {
      menus: [
        {
          title: "collections",
          link: "",
        },
        {
          title: "men",
          link: "",
        },
        {
          title: "women",
          link: "",
        },
        {
          title: "about",
          link: "",
        },
        {
          title: "contact",
          link: "",
        },
      ],
    };
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