<template>
  <div class="movie__tag">
    <ul>
      <li>
        <button @click="handleTagClick('전체')">전체</button>
      </li>
      <li>
        <button @click="handleTagClick('코미디')">코미디</button>
      </li>
      <li>
        <button @click="handleTagClick('액션')">액션</button>
      </li>
      <li>
        <button @click="handleTagClick('애니메이션')">애니메이션</button>
      </li>
      <li>
        <button @click="handleTagClick('판타지')">판타지</button>
      </li>
      <li>
        <button @click="handleTagClick('음악영화')">음악</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "MovieTag",
  methods: {
    handleTagClick(tag) {
      this.$emit("tag-click", tag);
    },
  },
};
</script>
