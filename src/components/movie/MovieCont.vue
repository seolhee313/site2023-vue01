<template>
  <div class="movie__cont container">
    <ul>
      <li v-for="(movie, index) in movies" :key="index">
        <a
          :href="`https://www.themoviedb.org/movie/${movie.id}`"
          target="_blank"
        >
          <img
            :src="`https://image.tmdb.org/t/p/w500/${movie.poster_path}`"
            alt="영화 포스터"
          />
          <em>
            <span class="title">{{ movie.title }}</span>
            <span class="star">{{ movie.vote_average }}</span>
          </em>
        </a>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    movies: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style lang="scss">
@import "../../assets/scss/setting/mixins.scss";

// movie__page
.movie__cont {
  ul {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    margin-bottom: 100px;
    li {
      width: 23.3333%;
      margin-bottom: 4%;
      position: relative;
      img {
        width: 100%;
        border-radius: 20px;
        box-shadow: 0px 10px 10px #00000022;
      }
      em {
        .title {
          font-size: 20px;
          padding: 3px 0;
          &:hover {
            text-decoration: underline;
            text-underline-position: under;
          }
        }
        .star {
          position: absolute;
          right: 20px;
          top: 20px;
          width: 40px;
          height: 40px;
          background-color: #fff;
          text-align: center;
          line-height: 40px;
          border-radius: 50%;
          font-size: 15px;
          color: #4b4bff;
        }
      }
      span {
        display: block;
        margin: 4px 0;
      }
    }
  }
}
</style>
