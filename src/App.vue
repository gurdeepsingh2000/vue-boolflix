<template>
  <div id= "App">
    <Header @search='searchMovie' />
    <Main :filmList="filmListFiltered"  :filmListFiltered="filmListFiltered" />
  </div>
</template>

<script>
import axios from 'axios';
import Header from "./components/Header.vue";
import Main from "./components/Main.vue";
  export default {
    name: 'App',
    components: {
    Header,
    Main
  },                                         
  data: function(){
      return{
        filmList: [],
        filmListFiltered: [],
        seriesList: []
        }
  },
    created(){
    axios.get('https://api.themoviedb.org/3/movie/popular?api_key=f9f2d73c3435d93318563278430d4304').then((results) => {
      this.filmList = results.data.results
      })
  },
  methods:{
    searchMovie(searchString){
      if(searchString.length === 0){
        return this.filmListFiltered = this.filmList
        
      }
        axios.get(`https://api.themoviedb.org/3/search/multi?api_key=f9f2d73c3435d93318563278430d4304&query=${searchString}`).then((results) => {
        this.filmListFiltered = results.data.results
      })
     },
    }
  }
    
</script>

<style lang="scss" scoped>
@import "/style/app.scss"
</style>