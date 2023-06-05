<template>
  <swiper :modules="[Virtual]" :slides-per-view="3" :space-between="50" virtual>
    <swiper-slide
      v-for="(slideContent, index) in slides"
      :key="index"
      :virtualIndex="index"
      >{{ slideContent }}</swiper-slide
    >
  </swiper>
</template>
<script>
import { Virtual } from "swiper";
import { Swiper, SwiperSlide } from "swiper/vue";

export default {
  components: {
    Swiper,
    SwiperSlide,
  },

  setup() {
    const slides = Array.from({ length: 1000 }).map(
      (el, index) => `Slide ${index + 1}`
    );
    return {
      slides,
      Virtual,
    };
  },
};
</script>

<style >
.swiper-slide {
  background: blue;
  border: 1px solid;
}
</style>