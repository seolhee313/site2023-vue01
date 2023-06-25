<template>
  <div class="youtube__cont container">
    <ul>
      <li v-for="(youtube, index) in youtubes" :key="index">
        <a
          :href="'https://www.youtube.com/watch?v=' + youtube.id.videoId"
          target="_blank"
          rel="noopener noreferrer"
        >
          <img :src="youtube.snippet.thumbnails.medium.url" alt="유튜브" />
          <span>{{ decodeHTMLEntities(youtube.snippet.title) }}</span>
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
    decodeHTMLEntities(text) {
      const entities = {
        "&amp;": "&",
        "&#38;": "&",
        "&#x26;": "&",
        "&lt;": "<",
        "&#60;": "<",
        "&#x3C;": "<",
        "&gt;": ">",
        "&#62;": ">",
        "&#x3E;": ">",
        "&quot;": '"',
        "&#34;": '"',
        "&#x22;": '"',
        "&#x27;": "'",
        "&#39;": "'",
        "&#x2019;": "'", // Added entity for apostrophe (’)
        "&#x201C;": '"', // Added entity for left double quotation mark (“)
        "&#x201D;": '"', // Added entity for right double quotation mark (”)
      };

      return text.replace(
        /&(amp|lt|gt|quot|#34|#x22|#x27|#39|#x2019|#x201C|#x201D);/g,
        (match) => entities[match]
      );
    },
  },
};
</script>

<style lang="scss">
@import "../../assets/scss/setting/mixins.scss";
.youtube__cont {
  ul {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    margin-bottom: 100px;

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
