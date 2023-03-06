<script>
export default {
  props: {
    title: String,
    originTitle: String,
    lingua: String,
    voto: String,
  },
};
</script>

<template>
  <div class="col text-center">
    <h3 class="my-3">{{ title }}</h3>
    <p class="my-1">{{ originTitle }}</p>
    <p class="my-1">{{ lingua }}</p>
    <p class="my-1">{{ voto }}</p>
  </div>
</template>

<style lang="scss" scoped>

</style>
