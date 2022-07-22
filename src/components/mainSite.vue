<template>
  <div id="mainSite">

    <div class="container">
      <movieSite :propFilmResultArray="propFilmResultArray" />
      <seriesSite :propTvResultArray="propTvResultArray" />
    </div>
  </div>


</template>





<script>
import movieSite from './movieSite.vue'
import seriesSite from './seriesSite.vue'

export default {
  components: {
    movieSite,
    seriesSite,
  },
  props: {
    propFilmResultArray: Array,
    propTvResultArray: Array,
  },
  data() {
    return {};
  },

}
</script>





<style lang="scss">
#mainSite {
  .container {
    .row {
      padding: 1rem 0;
      text-align: center;

      .filmHeader,
      .seriesHeader {
        margin: 2rem 0;

        ul {
          li {
            font-size: 1.5rem;
            letter-spacing: .2rem;
            font-family: Impact, Haettenschweiler, 'Arial Narrow Bold', sans-serif;
          }
        }
      }

      ul {
        list-style-type: none;
        justify-content: space-between;
        text-align: center;

        li {
          font-size: .6rem;
          font-weight: 800;
          margin: .5rem 0;
        }
      }
    }
  }
}
</style>
