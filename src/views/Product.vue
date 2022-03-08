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
                  to="/product/12"
                  class="rounded-lg ma-auto"
                  max-width="400"
                  @mouseover="updateProduct(i)"
                >
                  <v-img
                    :src="require(`../assets/image/${image.imageThumbnail}`)"
                  ></v-img>
                </v-card>
              </v-col>
            </v-row>
          </v-col>
          <v-col cols="6">
            <p>{{ title }}</p>
            <h1>{{ product }}</h1>
            <p>
              These low-profile sneakers are your perfect casual wear companion.
              Featuring a durable rubber outer sole, they’ll withstand
              everything the weather can offer
            </p>
            <p>50%</p>
            <p>$125.00</p>
            <p class="text--secondary text-decoration-line-through">$250.00</p>
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