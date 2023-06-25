<template>
  <div class="unsplash__tag container">
    <div>
      <ul>
        <li
          v-for="(tag, index) in unsplashTag"
          :key="index"
          :class="{ active: tag.name === activeTag }"
        >
          <button @click="btnClick(tag.name)">
            {{ tag.name }}
          </button>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      unsplashTag: [
        { name: "바다" },
        { name: "산" },
        { name: "하늘" },
        { name: "꽃" },
        { name: "나무" },
      ],
      activeTag: "", // 액티브 태그를 저장할 속성 추가
    };
  },
  methods: {
    btnClick(tagName) {
      this.activeTag = tagName; // 클릭한 태그를 액티브 태그로 설정
      this.$emit("onSearch", tagName);
    },
  },
};
</script>

<style lang="scss">
.unsplash__tag {
  ul {
    display: flex;
    justify-content: center;
    margin-top: 100px;
    margin-bottom: 90px;

    li {
      button {
        display: inline-block;
        border: 1px solid #4857ec;
        padding: 10px 30px;
        margin: 0 10px;
        color: #4857ec;
        background-color: #fff;
        cursor: pointer;
        transition: all 0.3s;
        // border-radius: 50px;

        &:hover {
          background-color: #4857ec;
          color: #fff;
        }
      }

      &.active {
        button {
          background-color: #4857ec;
          color: #fff;
          border-radius: 50px;
        }
      }
    }
  }
}
</style>
