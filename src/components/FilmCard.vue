<script>
export default {
  props: {
    title: String,
    originalTitle: String,
    lingua: String,
    voto: String,
    img: String,
  },
};
</script>

<template>
  <div>
    <h3>{{ title }}</h3>
    <p>{{ originalTitle }}</p>
    <p>{{ lingua }} </p>
    <img crossorigin="anonymous" :src="'https://countryflagsapi.com/png/' + lingua">
    <p>{{ voto }}</p>
    <img :src="'https://image.tmdb.org/t/p/w500' + img ">
  </div>
</template>

<style lang="scss" scoped>

template{
    color: white;
}

</style>
