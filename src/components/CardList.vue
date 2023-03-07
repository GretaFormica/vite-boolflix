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
      endpointmovie: "https://api.themoviedb.org/3/search/movie?api_key=409efcdb9caa94eda8ab94cbf9f11af3",
      endpointtv: "https://api.themoviedb.org/3/search/tv?api_key=409efcdb9caa94eda8ab94cbf9f11af3",

    }
  },

  components: {
    Search,
    FilmCard,
  },

  methods : {

    //film
    GenerazioneFilm(url) {
      axios
        .get(url)
        .then((response) => {
          console.log(response)
          store.film = response.data.results;
          console.log(store)
        })
    },


    filtered(term) {
      this.GenerazioneFilm(`${this.endpointmovie}&query=${term}`);
      this.GenerazioneSerie(`${this.endpointtv}&query=${term}`);
    },

    // serietv
    GenerazioneSerie(url) {
      axios
        .get(url)
        .then((response) => {
          console.log(response)
          store.serie = response.data.results;
          console.log(store)
        })
    },
  },

  created() {

    //film
    this.GenerazioneFilm(this.endpointmovie);

    //serietv
    this.GenerazioneSerie(this.endpointtv);

  },
};
</script>

<template>

  <Search @on-search="filtered"/>


  <!-- film -->
  <h1 class="text-danger">FILM</h1>
  <div class="row row-cols-3">

    <FilmCard
    v-for=" item in store.film"
    :title="item.title"
    :originalTitle="item.original_title"
    :lingua="item.original_language"
    :voto="item.vote_average"
    :img= "item.poster_path"
    />
  </div>

    <!-- serie -->
    <h1 class="text-danger">SERIE TV</h1>
    <div class="row row-cols-3">
      <FilmCard
      v-for=" item in store.serie"
      :title="item.original_name"
      :originalTitle="item.original_title"
      :lingua="item.original_language"
      :voto="item.vote_average"
      :img= "item.poster_path"
      />
    </div>
</template>

<style lang="scss" scoped></style>
https://image.tmdb.org/t/p/w500