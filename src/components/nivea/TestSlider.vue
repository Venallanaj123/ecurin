<template>
  <div class="gallery">
    <Carousel
      id="gallery-carousel"
      :items-to-show="1"
      :wrap-around="true"
      v-model="currentSlide"
      @slideChange="onSlideChange"
      ref="carousel"
    >
      <Slide v-for="(image, index) in images" :key="index">
        <div class="gallery__item">
          <img :src="image.src" />
        </div>
      </Slide>
      <Navigation slot="navigation" />
    </Carousel>

    <div class="gallery__thumbnails">
      <Carousel
        id="thumbnail-carousel"
        :items-to-show="4"
        :wrap-around="true"
        v-model="currentSlide"
        ref="carousel"
      >
        <Slide v-for="(image, index) in images" :key="index">
          <div class="gallery__thumbnail">
            <img :src="image.thumbnailSrc" @click="selectImage(index)" />
          </div>
        </Slide>
      </Carousel>
    </div>
  </div>
</template>

<script>
import { defineComponent } from "vue";
import { Carousel, Slide, Navigation } from "vue3-carousel";
import "vue3-carousel/dist/carousel.css";

export default defineComponent({
  name: "Gallery",
  components: { Carousel, Slide, Navigation },

  data: () => ({
    currentSlide: 0,
    images: [
      {
        src: require("../../assets/images/nivea/nive-1.jpg"),
        thumbnailSrc: require("../../assets/images/nivea/nive-1.jpg"),
      },
      {
        src: require("../../assets/images/nivea/nive-2.jpg"),
        thumbnailSrc: require("../../assets/images/nivea/nive-2.jpg"),
      },
      {
        src: require("../../assets/images/nivea/nive-3.jpg"),
        thumbnailSrc: require("../../assets/images/nivea/nive-3.jpg"),
      },
      {
        src: require("../../assets/images/nivea/nive-4.jpg"),
        thumbnailSrc: require("../../assets/images/nivea/nive-4.jpg"),
      },
    ],
  }),

  methods: {
    selectImage(index) {
      this.currentSlide = index;
    },

    onSlideChange() {},
  },
});
</script>

<style scoped>
.gallery__thumbnails {
  display: flex;
  justify-content: center;
  align-items: center;
  position: relative;
}

.gallery__thumbnail img {
  width: 100%;
  height: auto;
  cursor: pointer;
}

.carousel__slide--active > .gallery__thumbnail {
  border-bottom: 3px solid #0032a0;
}
.gallery__item img {
  width: 600px;
  height: auto;
}
.gallery__thumbnail {
  display: flex;
}
.gallery__thumbnail img {
  width: 100px;
  height: 100px;
}
</style>
