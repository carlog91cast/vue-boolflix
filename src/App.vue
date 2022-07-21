<template>
  <div id="app">
    <FlixHeader @search="movieSearch" />
    <FlixMain v-for="(movie, index) in movies" :key="index" :film = movie />
  </div>
</template>

<script>
import FlixHeader from './components/FlixHeader.vue';
import FlixMain from './components/FlixMain.vue';
import axios from 'axios';
import { setFlagsFromString } from 'v8';



export default {
  name: 'App',
  components: {
    FlixHeader,
    FlixMain,
  },
  data() {
    return {
      movies: [],

    }
  },
  methods: {
    movieSearch(searchInput) {
      axios.get(`https://api.themoviedb.org/3/search/movie?query=a&api_key=d0770c7faacf104886a30c991df47d08&query=${searchInput}`)
        .then((result) => {
          console.log(result.data.results)
          this.movies = result.data.results;
  
        })
        .catch((error) => {
          console.warn(error);
        })
    },
  },
  created(){
    this.movieSearch()
  },
  
}
</script >
  
<style lang="scss">
  @import "~bootstrap/scss/bootstrap";
</style>
