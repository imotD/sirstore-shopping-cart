<template>
  <div>
    <v-card class="mx-auto" max-width="344" outlined>
      <v-list-item three-line>
        <v-list-item-content>
          <v-list-item-title class="text-h5 mb-1">
            Nama Menu
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
        <v-btn small outlined rounded icon>
          <v-icon>mdi-minus</v-icon>
        </v-btn>
        <div class="mx-3">x 1</div>
        <v-btn small outlined rounded icon>
          <v-icon>mdi-plus</v-icon>
        </v-btn>
        <v-spacer></v-spacer>
        <v-btn small rounded icon>
          <v-icon>mdi-delete</v-icon>
        </v-btn>
      </v-card-actions>
    </v-card>
  </div>
</template>

<script>
export default {
  name: "Cart",
};
</script>

<style lang="scss" scoped>
</style>