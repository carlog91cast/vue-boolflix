<template>
  <div id="app">
    <FlixHeader @search="tvMoviesFunction" />
    <FlixMain :movies = "movies" :series = "series" />
  </div>
</template>

<script>
import FlixHeader from './components/FlixHeader.vue';
import FlixMain from './components/FlixMain.vue';
import axios from 'axios';



export default {
  name: 'App',
  components: {
    FlixHeader,
    FlixMain,
  },
  data() {
    return {
      apiKey: 'd0770c7faacf104886a30c991df47d08',
      apiMovieUrl: 'https://api.themoviedb.org/3/search/movie',
      apiTvUrl: 'https://api.themoviedb.org/3/search/tv',
      movies: [],
      series: [],

    }
  },
  methods: {
    movieSearch(searchInput) {
      axios.get(`${this.apiMovieUrl}?api_key=${this.apiKey}&query=${searchInput}`)
        .then((result) => {
          console.log(result.data.results)
          this.movies = result.data.results;
  
        })
        .catch((error) => {
          console.warn(error);
        })
    },
    tvSearch(searchInput) {
      axios.get(`${this.apiTvUrl}?api_key=${this.apiKey}&query=${searchInput}`)
        .then((result) => {
          console.log(result.data.results)
          this.series = result.data.results;
  
        })
        .catch((error) => {
          console.warn(error);
        })
    },
    tvMoviesFunction(searchInput){
      this.tvSearch(searchInput),
      this.movieSearch(searchInput)
    }
  }
  
}
</script >
  
<style lang="scss">
  @import "~bootstrap/scss/bootstrap";
</style>
