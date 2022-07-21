<template>
  <div id="app">
    <FlixHeader @search="movieSearch" />
    <FlixMain />
  </div>
</template>

<script>
import FlixHeader from './components/FlixHeader.vue';
import FlixMain from './components/FlixMain.vue';
import axios from 'axios';



export default {
  name: 'App',
  data() {
    return{
      movies:[],
      
    }
  },
  methods:{
    movieSearch(){
      
    }
  },
  components: {
    FlixHeader,
    FlixMain,
  }
}
</script>

<style>
</style>
