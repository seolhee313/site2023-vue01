<template>
  <div class="movie__tag">
    <ul>
      <li :class="{ active: activeTag === 'popular' }">
        <a
          @click="
            onClick('https://api.themoviedb.org/3/movie/popular', 'popular')
          "
          >인기 영화</a
        >
      </li>
      <li :class="{ active: activeTag === 'now_playing' }">
        <a
          @click="
            onClick(
              'https://api.themoviedb.org/3/movie/now_playing',
              'now_playing'
            )
          "
          >현재 상영</a
        >
      </li>
      <li :class="{ active: activeTag === 'upcoming' }">
        <a
          @click="
            onClick('https://api.themoviedb.org/3/movie/upcoming', 'upcoming')
          "
          >최근 영화</a
        >
      </li>
      <li :class="{ active: activeTag === 'popular_tv' }">
        <a
          @click="
            onClick('https://api.themoviedb.org/3/tv/popular', 'popular_tv')
          "
          >인기 TV SHOW</a
        >
      </li>
      <li :class="{ active: activeTag === 'top_rated_tv' }">
        <a
          @click="
            onClick('https://api.themoviedb.org/3/tv/top_rated', 'top_rated_tv')
          "
          >TV 순위</a
        >
      </li>
      <li :class="{ active: activeTag === 'on_the_air_tv' }">
        <a
          @click="
            onClick(
              'https://api.themoviedb.org/3/tv/on_the_air',
              'on_the_air_tv'
            )
          "
          >TV SHOW</a
        >
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      activeTag: "",
    };
  },
  methods: {
    onClick(value, tag) {
      this.activeTag = tag;
      this.$emit("on-search", value, tag);
    },
  },
};
</script>

<style lang="scss">
@import "../../assets/scss/setting/mixins.scss";
// movie__tag
.movie__tag {
  ul {
    display: flex;
    justify-content: center;
    margin-bottom: 50px;
    margin-top: 50px;
    padding: 50px 0 40px;

    li {
      a {
        font-family: "GmarketSans";
        border: 1px solid var(--button_green);
        padding: 10px 30px;
        margin: 0 10px;
        color: var(--button_green);
        cursor: pointer;
        transition: all 0.3s;
        &:hover {
          background-color: #00c183;
          color: #fff;
          // border-radius: 50px;
        }
      }
      &.active {
        a {
          background-color: #00c183;
          color: #fff;
          border-radius: 50px;
        }
      }
    }
  }
}
</style>
