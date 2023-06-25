<template>
  <Contents>
    <ContTitle title="artist" />
    <IntroCont />
  </Contents>
</template>

<script>
import ContTitle from "@/components/layout/ContTitle.vue";
import IntroCont from "@/components/intro/IntroCont.vue";

export default {
  components: {
    ContTitle,
    IntroCont,
  },
};
</script>
