<template>
  <div class="Mv__tag">
    <div v-for="(row, index) in dividedTags" :key="index">
      <button
        v-for="(tag, tagIndex) in row"
        :key="tagIndex"
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
  data() {
    return {
      mvTag: [
        { name: "블랙핑크" },
        { name: "BTS" },
        { name: "아이유" },
        { name: "트와이스" },
        { name: "태연" },
        { name: "세븐틴" },
        { name: "에스파" },
        { name: "뉴진스" },
        { name: "아이브" },
        { name: "르세라핌" },
        { name: "아이들" },
        { name: "NCT" },
        { name: "레드벨벳" },
        { name: "스테이씨" },
        { name: "소녀시대" },
        { name: "빅뱅" },
        { name: "슈퍼주니어" },
        { name: "엑소" },
      ],
      activeTag: "", // 선택된 태그를 저장할 데이터
    };
  },
  computed: {
    dividedTags() {
      const chunkSize = 10; // 한 줄에 표시할 버튼 수
      const divided = [];
      let currentRow = [];
      for (let i = 0; i < this.mvTag.length; i++) {
        currentRow.push(this.mvTag[i]);
        if (currentRow.length === chunkSize) {
          divided.push(currentRow);
          currentRow = [];
        }
      }
      if (currentRow.length > 0) {
        divided.push(currentRow);
      }
      return divided;
    },
  },
  methods: {
    btnClick(tag) {
      this.activeTag = tag; // 선택된 태그를 activeTag에 설정
      this.$emit("search", tag);
    },
  },
};
</script>

<style lang="scss">
.Mv__tag {
  div {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    // margin-top: 100px;
    margin-bottom: 20px;

    button {
      border: 1px solid #00c183;
      padding: 10px 20px;
      margin: 0 10px;
      margin-bottom: 10px;
      color: #00c183;
      background-color: #fff;
      cursor: pointer;

      &:hover {
        background-color: #00c183;
        color: #fff;
      }

      &.active {
        color: #fff;
        background-color: #00c183;
        border-radius: 50px;
      }
    }
  }
}
</style>
