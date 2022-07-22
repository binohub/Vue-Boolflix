<template>
  <div id="app">

    <headerSite @parentSearch="functionSearch" />
    <mainSite 
    :propTvResultArray="tvResultArray"
    :propFilmResultArray='filmResultArray'  />

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
      //! IMPORT AXIOS BEFORE
      apiSearch: 'https://api.themoviedb.org/3/search/',
      apiMovie: 'movie?',
      apiSeries: 'tv?',
      apiKey: 'api_key=12ee404a8bdcc1b9710ad43bccb87cd6',
      addQuery: '&query=',
      // userQuery: 'xanax',

      // ! SEARCH E' LA VERSIONE DINAMICA DI USER QUERY
      search: '',
      filmResultArray: [],
      tvResultArray: [],
    }
  },



  methods: {

    getFilms() {
      axios.get(
        //! STA CREANDO IL LINK DINAMICO
        this.apiSearch +
        this.apiMovie +
        this.apiKey +
        this.addQuery +
        //! DYNAMIC REQUEST
        this.search
        //TODO SEARCH DA COLLEGARE AL SEARCH INPUT => HEADER
      )
        .then((response) => {
          console.log(`hai cercato il film... ${this.search}`);
          this.filmResultArray = response.data.results;
          console.log(`query on working... attendi risposta`);
          console.log(`risposta ottenuta! sto popolando l'array... (filmResultArray)`);
          console.log(this.filmResultArray);
        })
        .catch((error) => {
          console.warn(error);
        })
    },
    getSeries() {
      axios.get(
        //! STA CREANDO IL LINK DINAMICO
        this.apiSearch +
        this.apiSeries +
        this.apiKey +
        this.addQuery +
        //! DYNAMIC REQUEST
        this.search
        //TODO SEARCH DA COLLEGARE AL SEARCH INPUT => HEADER
      )
        .then((response) => {
          console.log(`hai cercato la serie tv... ${this.search}`);
          this.tvResultArray = response.data.results;
          console.log(`query on working... attendi risposta`);
          console.log(`risposta ottenuta! sto popolando l'array... (tvResultArray)`);
          console.log(this.tvResultArray);
        })
        .catch((error) => {
          console.warn(error);
        })
    },

    functionSearch(search) {
      this.search = search;
      console.warn(this.search);
      this.getFilms();
      this.getSeries();
    }
  },



  mounted() {
  },
}
</script>





<style lang="scss">
@import "~bootstrap/scss/bootstrap.scss";
</style>
