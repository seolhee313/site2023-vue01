<template>
  <div>
    <ContTitle title="unsplash" />
    <UnsplashSlider :images="images" />
    <UnsplashSearch @onSearch="search" />
    <UnsplashTag @onSearch="search" />
    <UnsplashCont :images="filteredImages" />
  </div>
</template>

<script>
import ContTitle from "@/components/layout/ContTitle.vue";
import UnsplashSlider from "@/components/unsplash/UnsplashSlider.vue";
import UnsplashSearch from "@/components/unsplash/UnsplashSearch.vue";
import UnsplashTag from "@/components/unsplash/UnsplashTag.vue";
import UnsplashCont from "@/components/unsplash/UnsplashCont.vue";
import { ref, onMounted } from "vue";

export default {
  components: {
    ContTitle,
    UnsplashSlider,
    UnsplashSearch,
    UnsplashTag,
    UnsplashCont,
  },

  setup() {
    const images = ref([]);
    const filteredImages = ref([]);

    const search = async (query) => {
      await fetch(
        `https://api.unsplash.com/search/photos?client_id=Z_tjioEc226tuq445cyzydcEhf22Ej-cGt8GA5TaUyE&per_page=30&query=${query}`
      )
        .then((response) => response.json())
        .then((responseData) => {
          images.value = responseData.results;
          filteredImages.value = responseData.results;
        })
        .catch((error) => {
          console.error("Error:", error);
        });
    };

    const loadImages = async () => {
      await fetch(
        "https://api.unsplash.com/photos?client_id=Z_tjioEc226tuq445cyzydcEhf22Ej-cGt8GA5TaUyE&per_page=30"
      )
        .then((response) => response.json())
        .then((result) => {
          images.value = result;
          filteredImages.value = result;
        })
        .catch((error) => console.log(error));
    };

    onMounted(() => {
      loadImages();
    });

    return {
      images,
      filteredImages,
      search,
    };
  },
};
</script>
