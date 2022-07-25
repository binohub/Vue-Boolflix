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
    overflow-x: auto;
    .row {
      padding: 1rem 0;
      text-align: center;
      color: white;



      .filmHeader,
      .seriesHeader {
        margin: 2rem 0;
      }
      .cardUp{
        margin: 1rem 0;
        min-height: 250px;
      }
      .netCard:hover .cardDown{
        visibility: visible;
      }
        .netCard:hover .cardUp{
        visibility: hidden;
      }
      .cardDown{
        top: 10%;
        bottom: 10%;
        visibility: hidden;
      }
      ul {
        list-style-type: none;
        text-align: start;

        li {
          font-size: .5rem;
          margin: 1.2rem 0;

          span.descCard {
            color: red;
          }

          img {
            height: 20px;
            width: 20px;
          }

        }
      }
    }
  }
}
</style>
