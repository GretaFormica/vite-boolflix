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
  <div class="carta">
        <img :src="'https://image.tmdb.org/t/p/w342' + img " class="poster">
        <div class="text">
            <h3> <b> Titolo: </b> {{ title }}</h3>
            <p> <b> Titolo otiginale: </b> {{ originalTitle }}</p>
            <img crossorigin="anonymous" :src="'https://countryflagsapi.com/png/' + lingua" class="bandiera">
            <p class="my-3"> <b> Voto: </b> {{ voto }}</p>
        </div>
  </div>
</template>

<style lang="scss" scoped>

.poster{
    height: 500px;
    width: 300px;
    object-fit: contain;
}

.text{
    display: none;
    *{
        display: none;
    }
}

.carta:hover{

    .poster{
        display: none;
    }

    .text{
        display: block;
        padding: 50spx;

        *{
            display: block;
        }
    }
}

.bandiera{
    width: 30px;
}

</style>
