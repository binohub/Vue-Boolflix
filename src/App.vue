<template>
  <div id="app">

    <headerSite @channelSearch="functionSearch" />
    <mainSite />

  </div>
</template>

<script>
import axios from 'axios'
import headerSite from './components/headerSite.vue'
import mainSite from './components/mainSite.vue'

export default {
  name: 'App',
  components: {
    headerSite,
    mainSite,
  },
  data() {
    return {
      search: '',
      apiSearch: 'https://api.themoviedb.org/3/search/',
      apiMovie: 'movie?',
      apiKey: 'api_key=fc7176f21c9d0e2ebc73ae83e20968a4',
      addQuery: '&query=',
      // userQuery: 'xanax',
      filmResultArray: [],
    }
  },
  methods: {

    getFilms() {
      axios.get(
        this.apiSearch +
        this.apiMovie +
        this.apiKey +
        this.addQuery +
        this.search
      )
        .then((response) => {
          this.filmResultArray = response.data.results;
          console.log(this.filmResultArray);
        })
        .catch((error) => {
          console.log(error);
        })
    },

    functionSearch(input) {
      this.search = input;
      console.warn(this.search);
      this.getFilms();
    }
  },
  mounted(){

  },
}
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap.scss";
</style>
