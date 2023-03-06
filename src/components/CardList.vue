<script>
import Search from "./Search.vue";
import FilmCard from "./FilmCard.vue";
import { store } from './store';
import axios from "axios";


export default {
  data() {
    return {
      store,
      title: "Cardlist",
      endpoint: "https://api.themoviedb.org/3/search/movie?api_key=409efcdb9caa94eda8ab94cbf9f11af3"

    }
  },

  components: {
    Search,
    FilmCard,
  },

  methods : {

    GenerazioneFilm(url) {
      axios
        .get(url)
        .then((response) => {
          console.log(response)
          store.film = response.data.results;
          console.log(store)
        })
    },


    filteredFilm(term) {
      this.GenerazioneFilm(`${this.endpoint}&query=${term}`);
    },
  },

  created() {
    this.GenerazioneFilm(this.endpoint);
  },
};
</script>

<template>
  <p>{{ title }}</p>

  <Search @on-search="filteredFilm"/>


  <FilmCard
      v-for=" item in store.film"
      :title="item.title"
      :originalTitle="item.original_title"
      :lingua="item.original_language"
      :voto="item.vote_average"
    />
</template>

<style lang="scss" scoped></style>