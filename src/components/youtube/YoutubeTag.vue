<template>
  <div class="youtube__tag">
    <ul>
      <li>
        <button @click="handleTagClick('전체')">전체</button>
      </li>
      <li>
        <button @click="handleTagClick('음악')">음악</button>
      </li>
      <li>
        <button @click="handleTagClick('뮤직비디오')">뮤직비디오</button>
      </li>
      <li>
        <button @click="handleTagClick('라이브')">라이브</button>
      </li>
      <li>
        <button @click="handleTagClick('피아노')">피아노</button>
      </li>
      <li>
        <button @click="handleTagClick('기타')">기타</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "YoutubeTag",
  methods: {
    handleTagClick(tag) {
      this.$emit("tag-click", tag);
    },
  },
};
</script>
