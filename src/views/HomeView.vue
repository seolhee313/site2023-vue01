<template>
  <main>
    <SliderSection attr="slider__wrap section score5" />
    <IntroSection attr="intro__wrap score5 section bg-blue" />
    <MvSection attr="mv__wrap section score5 center" />
    <YoutubeSection attr="youtube__wrap score5 section bg-blue" />
    <UnsplashSection attr="unsplash__wrap score5 section" />
    <MovieSection attr="movie__wrap score5 section bg-blue" />
  </main>
</template>

<script>
// @ is an alias to /src
import SliderSection from "@/components/section/SliderSection.vue";
import IntroSection from "@/components/section/IntroSection.vue";
import MvSection from "@/components/section/MvSection.vue";
import YoutubeSection from "@/components/section/YoutubeSection.vue";
import UnsplashSection from "@/components/section/UnsplashSection.vue";
import MovieSection from "@/components/section/MovieSection.vue";

export default {
  components: {
    SliderSection,
    IntroSection,
    MvSection,
    YoutubeSection,
    UnsplashSection,
    MovieSection,
  },
};
</script>
