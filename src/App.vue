<script>
import Header from './components/Header.vue';
import Main from './components/Main.vue';
import { store } from './components/store/';

export default {
  data() {
    return {
      store,
    }
  },

  components: {
    Header,
    Main,
  },

  // created() {
  //   axios
  //   .get("https://api.themoviedb.org/3/movie/550?api_key=409efcdb9caa94eda8ab94cbf9f11af3")
  //   .then((response) => {
  //     store.film = response.data.results;
  //   })
  // }
};
</script>

<template>
  <Header />
  <Main />
  
</template>

<style lang="scss">

@use "./components/style.scss"

</style>
