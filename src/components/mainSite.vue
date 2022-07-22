<template>

  <div id="mainSite">
    <div class="container">
      <div class="row">

        <div class="filmHeader">
          <ul>
            <li class="col-3">
              Title
            </li>
            <li class="col-3">
              Original Title
            </li>
            <li class="col-3">
              Original Language
            </li>
            <li class="col-3">
              Vote Count
            </li>
          </ul>

        </div>


        <ul v-for="film in propFilmResultArray" :key="film.id">
          <li class="col-3">
            {{ film.title }}
          </li>
          <li class="col-3">
            {{ film.original_title }}
          </li>
          <li class="col-3">
            {{ film.original_language }}
          </li>
          <li class="col-3">
            {{ film.vote_count }}
          </li>
        </ul>

      </div>
    </div>
  </div>

</template>





<script>
export default {
  props: {
    propFilmResultArray: Array,
  },



  data() {
    return {
    }
  },



  methods: {
  },



  mounted() {
  },
}
</script>





<style scoped lang="scss">
#mainSite {
  .container {
    .row {
      padding: 5rem 0;

      .filmHeader {
        ul{
          li{
            font-size: 1.5rem;
            letter-spacing: .2rem;
            font-family: Impact, Haettenschweiler, 'Arial Narrow Bold', sans-serif;
          }
        }
      }

      ul {
        list-style-type: none;
        display: flex;
        justify-content: space-between;
        text-align: center;
        padding: 3rem 0;

        li {
          font-weight: 600;
          padding: 0 1rem;
        }
      }
    }
  }
}
</style>
