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
      color: white;



      .filmHeader,
      .seriesHeader {
        margin: 2rem 0;

        // ul {
        //   li {
        //     font-size: 1.5rem;
        //     letter-spacing: .2rem;
        //     font-family: Impact, Haettenschweiler, 'Arial Narrow Bold', sans-serif;
        //   }
        // }
      }

      .cardUp img {
        position: relative;
        border-radius: 15px;
        z-index: 2;
      }

      .cardUp img:active {
        z-index: -1;
      }

      .cardDown ul {
        position: relative;
        bottom: 200px;
      }

      ul {
        list-style-type: none;
        justify-content: space-between;
        text-align: center;
        padding: .2rem;

        li {
          font-size: .5rem;

          span.descCard{
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
