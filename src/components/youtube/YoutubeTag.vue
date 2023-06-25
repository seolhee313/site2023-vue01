<template>
  <div class="youtube__tag">
    <div>
      <button
        v-for="(tag, index) in youtubeTags"
        :key="index"
        :class="{ active: tag.name === activeTag }"
        @click="btnClick(tag.name)"
      >
        {{ tag.name }}
      </button>
    </div>
  </div>
</template>

<script>
export default {
  props: ["onSearch"],
  data() {
    return {
      youtubeTags: [
        { name: "K-POP" },
        { name: "팝송" },
        { name: "힙합" },
        { name: "알앤비" },
        { name: "플레이리스트" },
      ],
      activeTag: "", // 선택된 태그를 저장할 데이터
    };
  },
  methods: {
    btnClick(name) {
      this.activeTag = name; // 선택된 태그를 activeTag에 설정
      this.onSearch(name);
    },
  },
};
</script>

<style lang="scss">
@import "../../assets/scss/setting/mixins.scss";
// youtube__tag
.youtube__tag {
  div {
    display: flex;
    justify-content: center;
    margin-bottom: 50px;
    margin-top: 50px;

    button {
      border: 1px solid var(--button_red);
      padding: 10px 20px;
      margin: 0 10px;
      color: var(--button_red);
      cursor: pointer;
      background-color: #fff;
      transition: all 0.3s;

      &:hover {
        background-color: #ff3344;
        color: #fff;
      }
    }

    button.active {
      background-color: #ff3344;
      color: #fff;
      border-radius: 50px;
    }
  }
}
</style>
