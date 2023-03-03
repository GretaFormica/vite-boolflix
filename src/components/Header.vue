<script>
import Search from "./Search.vue";

export default {
  data() {
    return {
      title: "Header"
    }
  },

  components: {
    Search,
  },
};
</script>

<template>
  <h1>{{ title }}</h1>

  <Search />
</template>

<style lang="scss" scoped></style>
