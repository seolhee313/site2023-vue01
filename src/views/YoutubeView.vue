<template>
  <ContTitle title="youtube" />
  <YoutubeSlider :youtubes="youtubes" />
  <YoutubeSearch @search="SearchYoutube" />
  <YoutubeTag @search="SearchYoutube" />
  <YoutubeCont :youtubes="youtubes" />
</template>

<script>
import ContTitle from "@/components/layout/ContTitle.vue";
import YoutubeSlider from "@/components/youtube/YoutubeSlider.vue";
import YoutubeSearch from "@/components/youtube/YoutubeSearch.vue";
import YoutubeTag from "@/components/youtube/YoutubeTag.vue";
import YoutubeCont from "@/components/youtube/YoutubeCont.vue";
import { ref } from "vue";

export default {
  components: {
    ContTitle,
    YoutubeSlider,
    YoutubeSearch,
    YoutubeTag,
    YoutubeCont,
  },

  setup() {
    const youtubes = ref([]);

    const TopYoutubes = () => {
      fetch(
        "https://youtube.googleapis.com/youtube/v3/search?part=snippet&maxResults=28&q=cover&type=video&key=AIzaSyCuRG9CovWM7isuZ0RmIH9xoIee0WBetiA"
      )
        .then((response) => response.json())
        .then((result) => {
          youtubes.value = result.items.map((item) => ({
            ...item,
            snippet: {
              ...item.snippet,
              title: removeSpecialCharacters(item.snippet.title),
            },
          }));
        })
        .catch((error) => console.log(error));
    };
    TopYoutubes();

    const SearchYoutube = async (query) => {
      await fetch(
        `https://youtube.googleapis.com/youtube/v3/search?part=snippet&maxResults=28&q=${query}&type=video&key=AIzaSyCuRG9CovWM7isuZ0RmIH9xoIee0WBetiA`
      )
        .then((response) => response.json())
        .then((result) => {
          youtubes.value = result.items.map((item) => ({
            ...item,
            snippet: {
              ...item.snippet,
              title: removeSpecialCharacters(item.snippet.title),
            },
          }));
        })
        .catch((error) => console.log("error", error));
    };

    const removeSpecialCharacters = (text) => {
      const regex = /[^\w\sㄱ-ㅎㅏ-ㅣ가-힣]/g;
      return text.replace(regex, "");
    };

    return {
      youtubes,
      TopYoutubes,
      SearchYoutube,
    };
  },
};
</script>
