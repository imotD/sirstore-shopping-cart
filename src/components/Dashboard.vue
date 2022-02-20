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
      <v-col v-for="i in 6" :key="i" cols="4">
        <v-card :loading="loading" max-width="374">
          <v-img
            height="250"
            src="https://cdn.vuetifyjs.com/images/cards/cooking.png"
          ></v-img>

          <v-card-title>Cafe Badilico</v-card-title>

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
              Small plates, salads & sandwiches - an intimate setting with 12
              indoor seats plus patio seating.
            </div>
          </v-card-text>

          <v-divider class="mx-4"></v-divider>
          <v-card-actions>
            <div class="font-weight-medium">$ 30</div>
            <v-spacer></v-spacer>
            <v-btn color="orange lighten-2" dark> Add to cart </v-btn>
          </v-card-actions>
        </v-card>
      </v-col>
    </v-row>
  </div>
</template>

<script>
export default {
  name: "Dashboard",
  data() {
    return {};
  },
};
</script>

