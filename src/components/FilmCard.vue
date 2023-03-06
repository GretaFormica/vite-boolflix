<script>
export default {
  props: {
    title: String,
    originalTitle: String,
    lingua: String,
    voto: String,
  },
};
</script>

<template>
  <div>
    <h3>{{ title }}</h3>
    <p>{{ originalTitle }}</p>
    <p>{{ lingua }} </p>
    <p>{{ voto }}</p>
  </div>
</template>

<style lang="scss" scoped>

template{
    color: white;
}

</style>
