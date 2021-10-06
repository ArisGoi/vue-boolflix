<template>
  <div id="app">
    <Header @search="searchFilms"/>
    <Films :films="filmslist"/>
  </div>
</template>

<script>
import axios from 'axios'
import Header from './components/Header.vue'
import Films from './components/Films.vue'

export default {
  name: 'App',
  components: {
    Header,
    Films,
  },
  data(){
    return{
      filmslist:[]
    }
  },
  methods:{
    searchFilms(elm){
      console.log(elm);

      axios.get('https://api.themoviedb.org/3/search/movie/', {
        params: {
          api_key: '15c747bf94794250a1d04664229e8417',
          query: elm,
          language: 'it-IT'
        }
      }).then((resp) => {
        console.log(resp.data);
        this.filmslist = resp.data.results;
      })

    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
