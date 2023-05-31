<template>
  <section class="product-detail">
    <div class="container">
      <div class="row">
        <div class="col span_1_of_2">
          <div class="product-detail__carousel">
            <div class="product-detail__stage">
              <div class="product-detail__image">
                <img :src="images[activeImage].full" alt="image" />
              </div>
            </div>
            <div class="product-detail__thumbnails">
              <div
                v-for="(image, index) in images"
                :key="image.id"
                :class="[
                  'thumbnail-image',
                  activeImage == index ? 'active' : '',
                ]"
                @click="activateImage(index)"
              >
                <img :src="image.thumb" />
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "AppNivea",
  data() {
    return {
      showTooltip: false,
      activeImage: 0,
      //   totalImages: 5,

      images: [
        {
          id: 1,
          thumb: require("../../assets/images/nivea/nive-1.jpg"),
          full: require("../../assets/images/nivea/nive-1.jpg"),
        },
        {
          id: 2,
          thumb: require("../../assets/images/nivea/nive-2.jpg"),
          full: require("../../assets/images/nivea/nive-2.jpg"),
        },
        {
          id: 3,
          thumb: require("../../assets/images/nivea/nive-3.jpg"),
          full: require("../../assets/images/nivea/nive-3.jpg"),
        },
      ],
    };
  },

  mounted() {
    this.totalImages = this.images.length;
  },
  methods: {
    nextImage() {
      this.activeImage =
        this.activeImage < this.totalImages - 1 ? this.activeImage + 1 : 0;
    },
    prevImage() {
      this.activeImage =
        this.activeImage > 0 ? this.activeImage - 1 : this.totalImages - 1;
    },
    activateImage(index) {
      this.activeImage = index;
    },
  },
};
</script>

<style scoped lang="scss">
@import "../assets/scss/grid/grid";
.hr {
  display: block;
  margin: 30px 0;
  border: 0;
  border-bottom: 1px solid red($color: #000000);
  height: 1px;
}
</style>
