<template>
  <div>
  </div>
</template>

<script>
import axios from 'axios'

export default {

  data() {
    return {
      apiSearch: 'https://api.themoviedb.org/3/search/',
      apiMovie: 'movie?',
      apiKey: 'api_key=fc7176f21c9d0e2ebc73ae83e20968a4',
      addQuery: '&query=',
      userQuery: 'xanax',
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
        this.userQuery
      )
        .then((response) => {
          this.filmResultArray = response.data.results;
          console.log(this.filmResultArray);
        })
        .catch((error) => {
          console.log(error);
        })
    },
  },
  mounted() {
    this.getFilms()
  },


}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
</style>
