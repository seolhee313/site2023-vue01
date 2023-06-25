<template>
  <div className="movie__slider">
    <swiper
      :slides-per-view="1"
      :space-8between="50"
      :autoplay="{
        delay: 3000,
        disableOnInteraction: false,
      }"
      navigation
      :parallax="true"
      :pagination="{ clickable: true }"
      :scrollbar="{ draggable: true }"
      :loop="true"
      :modules="modules"
      @swiper="onSwiper"
      @slideChange="onSlideChange"
    >
      <swiper-slide v-for="(movie, index) in movies" :key="index">
        <a :href="`https://www.themoviedb.org/movie/${movie.id}`">
          <img
            :src="`https://image.tmdb.org/t/p/w1280/${movie.backdrop_path}`"
            :alt="movie.title"
          />
        </a>
      </swiper-slide>
      ...
    </swiper>
  </div>
</template>
<script>
import { Navigation, EffectFade, Autoplay, Parallax } from "swiper";
import { Swiper, SwiperSlide } from "swiper/vue";

import "swiper/css";
import "swiper/css/navigation";
import "swiper/css/pagination";
import "swiper/css/effect-fade";
export default {
  props: {
    movies: {
      type: Array,
      required: true,
    },
  },
  // 스와이퍼
  components: {
    Swiper,
    SwiperSlide,
  },
  setup() {
    const onSwiper = (swiper) => {
      console.log(swiper);
    };
    const onSlideChange = () => {
      console.log("slide change");
    };
    return {
      onSwiper,
      onSlideChange,
      modules: [Navigation, EffectFade, Autoplay, Parallax],
    };
  },
};
</script>
<style lang="scss">
.movie__slider {
  margin-bottom: 100px;
  a {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    img {
      object-fit: cover;
      // object-fit: cover;
      width: 1500px;
      height: 750px;
    }
  }
}
</style>
