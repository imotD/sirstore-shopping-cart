<template>
  <div>
    <v-app-bar fixed dark elevate-on-scroll>
      <v-toolbar flat>
        <v-toolbar-title class="font-weight-bold"> Sirstore </v-toolbar-title>

        <v-spacer></v-spacer>
        <v-btn icon fab flat>
          <v-icon> mdi-cart-variant </v-icon>
        </v-btn>
      </v-toolbar>
    </v-app-bar>
  </div>
</template>

<script>
export default {
  name: "Navbar",
  data() {
    return {};
  },
};
</script>

<style lang="scss" scoped>
</style>