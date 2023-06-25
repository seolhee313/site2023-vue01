<template>
  <div class="mv__cont container">
    <ul>
      <li v-for="(youtube, index) in youtubes" :key="index">
        <a
          :href="'https://www.youtube.com/watch?v=' + youtube.id.videoId"
          target="_blank"
          rel="noopener noreferrer"
        >
          <img :src="youtube.snippet.thumbnails.medium.url" alt="youtube" />
          <span v-html="decodeEntities(youtube.snippet.title)"></span>
        </a>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    youtubes: {
      type: Array,
      required: true,
    },
  },
  methods: {
    decodeEntities(text) {
      const txt = document.createElement("textarea");
      txt.innerHTML = text;
      return txt.value;
    },
  },
};
</script>

<style lang="scss">
@import "../../assets/scss/setting/mixins.scss";
.mv__cont {
  ul {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    margin-bottom: 100px;
    margin-top: 90px;

    li {
      width: 24%;
      margin-bottom: 4%;

      img {
        width: 100%;
        border-radius: 20px;
      }

      span {
        display: block;
        margin: 4px 0;
        overflow: hidden;
        text-overflow: ellipsis;
        white-space: nowrap;
      }
    }
  }
}

.youtube__tag {
  ul {
    display: flex;
    justify-content: center;
    margin-top: 100px;
    margin-bottom: 50px;

    li {
      button {
        border: 1px solid #4857ec;
        padding: 10px 20px;
        margin: 0 10px;
        color: #4857ec;
        background-color: #fff;
        cursor: pointer;
      }
    }
  }
}
</style>
