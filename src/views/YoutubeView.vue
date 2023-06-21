<template>
  <div>
    <ContTitle title="youtubes" />
    <YoutubeSlider />
    <YoutubeSearch />
    <YoutubeTag />
    <YoutubeCont :youtubes="youtubes" />
  </div>
</template>

<script>
import ContTitle from "@/components/layout/ContTitle.vue";
import YoutubeSlider from "@/components/youtube/YoutubeSlider.vue";
import YoutubeSearch from "@/components/youtube/YoutubeSearch.vue";
import YoutubeTag from "@/components/youtube/YoutubeTag.vue";
import YoutubeCont from "@/components/youtube/YoutubeCont.vue";
import { ref, onMounted } from "vue";

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

    const TopYoutubes = async () => {
      try {
        const response = await fetch(
          "https://youtube.googleapis.com/youtube/v3/search?part=snippet&maxResults=28&q=kpop&type=video&key=AIzaSyCuRG9CovWM7isuZ0RmIH9xoIee0WBetiA"
        );
        const result = await response.json();
        youtubes.value = result.items;
      } catch (error) {
        console.log("Error:", error);
      }
    };

    onMounted(TopYoutubes);

    return {
      youtubes,
      TopYoutubes,
    };
  },
};
</script>
