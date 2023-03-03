<script>
import CardList from "./CardList.vue";

export default {
  data() {
    return {
      title: "Main"
    }
  },

  components: {
    CardList,
  },
};
</script>

<template>
  <h1>{{ title }}</h1>

  <CardList />
</template>

<style lang="scss" scoped></style>