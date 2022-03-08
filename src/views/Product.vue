<template>
  <div>
    <Navbar />
    <section class="home">
      <v-container>
        <v-row>
          <v-col cols="6">
            <v-row>
              <v-col cols="12">
                <v-card
                  to="/product/12"
                  class="rounded-lg ma-auto"
                  max-width="400"
                >
                  <v-img
                    src="../assets/image/image-product-1.jpg"
                    height="400"
                    max-height="400"
                  ></v-img>
                </v-card>
              </v-col>
            </v-row>
            <v-row align="center" justify="center" dense>
              <v-col cols="2" class="ma-1 my-2" v-for="so in 4" :key="so">
                <v-card
                  to="/product/12"
                  class="rounded-lg ma-auto"
                  max-width="400"
                >
                  <v-img src="../assets/image/image-product-1.jpg"></v-img>
                </v-card>
              </v-col>
            </v-row>
          </v-col>
          <v-col cols="6">
            <p>Sneaker Company</p>
            <h1>Fall Limited Edition Sneakers</h1>
            <p>
              These low-profile sneakers are your perfect casual wear companion.
              Featuring a durable rubber outer sole, they’ll withstand
              everything the weather can offer
            </p>
            <p>$125.00 50% $250.00 0</p>
            <v-btn color="warning">Add to cart</v-btn>
          </v-col>
        </v-row>
      </v-container>
    </section>
  </div>
</template>

<script>
import Navbar from "@/components/Navbar.vue";
export default {
  name: "Product",
  components: {
    Navbar,
  },
};
</script>

<style lang="scss" scoped>
</style>