<template>
  <div>
    <Navbar />
    <section class="home">
      <v-container>
        <v-row align="center">
          <v-col cols="6">
            <v-row>
              <v-col cols="12">
                <v-card class="rounded-lg ma-auto" max-width="400">
                  <v-img
                    :src="image"
                    height="400"
                    max-height="400"
                    aspect-ratio="1"
                  ></v-img>
                </v-card>
              </v-col>
            </v-row>
            <v-row align="center" justify="center" dense>
              <v-col
                cols="2"
                class="ma-1 my-2"
                v-for="(image, i) in images"
                :key="i.imageId"
              >
                <v-card
                  :class="i == selectImage ? 'active__card' : ''"
                  class="rounded-lg ma-auto"
                  max-width="400"
                  @mouseover="updateProduct(i)"
                >
                  <v-img
                    :class="i == selectImage ? 'active__img' : ''"
                    :src="require(`../assets/image/${image.imageThumbnail}`)"
                  ></v-img>
                </v-card>
              </v-col>
            </v-row>
          </v-col>
          <v-col cols="6" class="home__description">
            <p class="label">{{ title }}</p>
            <h1>{{ product }}</h1>
            <br />
            <p class="text--secondary">
              These low-profile sneakers are your perfect casual wear companion.
              Featuring a durable rubber outer sole, they’ll withstand
              everything the weather can offer.
            </p>
            <div class="d-flex align-center">
              <div>
                <h1 class="font-weight-bold text-h4">$125.00</h1>
              </div>
              <div>
                <v-chip
                  class="
                    ml-3
                    orange
                    lighten-4
                    orange--text
                    font-weight-bold
                    text-button
                  "
                  label
                >
                  50%
                </v-chip>
              </div>
            </div>

            <p
              class="
                text-subtitle-1 text--secondary text-decoration-line-through
                font-weight-bold
              "
            >
              $ 250.00
            </p>
            <div class="d-flex">
              <div>
                <v-btn-toggle borderless dense>
                  <v-btn>
                    <v-icon small color="orange darken-4">mdi-minus</v-icon>
                  </v-btn>
                  <v-btn class="font-weight-bold btn-disabled"> 0 </v-btn>
                  <v-btn>
                    <v-icon small color="orange darken-4">mdi-plus</v-icon>
                  </v-btn>
                </v-btn-toggle>
              </div>
              <div class="ml-3">
                <v-btn
                  color="orange darken-2"
                  dark
                  class="font-weight-bold text-capitalize"
                >
                  <v-icon small class="pr-2">mdi-cart</v-icon>
                  Add to cart
                </v-btn>
              </div>
            </div>
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
  data() {
    return {
      title: "Sneaker Company",
      product: "Fall Limited Edition Sneakers",
      selectImage: 0,
      images: [
        {
          imageId: 1,
          imageProduct: "image-product-1.jpg",
          imageThumbnail: "image-product-1-thumbnail.jpg",
        },
        {
          imageId: 2,
          imageProduct: "image-product-2.jpg",
          imageThumbnail: "image-product-2-thumbnail.jpg",
        },
        {
          imageId: 3,
          imageProduct: "image-product-3.jpg",
          imageThumbnail: "image-product-3-thumbnail.jpg",
        },
        {
          imageId: 4,
          imageProduct: "image-product-4.jpg",
          imageThumbnail: "image-product-4-thumbnail.jpg",
        },
      ],
    };
  },
  methods: {
    updateProduct(index) {
      this.selectImage = index;
    },
  },
  computed: {
    image() {
      return require(`../assets/image/${
        this.images[this.selectImage].imageProduct
      }`);
    },
  },
};
</script>

<style lang="scss" scoped>
</style>