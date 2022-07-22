<template>

  <div id="mainSite">
    <div class="container">
      <div class="row">

        <ul>

          <li class="col-3">
            <h5>Titolo</h5>
          </li>
          <li class="col-3">
            <h5>Titolo Originale</h5>
          </li>
          <li class="col-3">
            <h5>Lingua</h5>
          </li>
          <li class="col-3">
            <h5>Voto</h5>
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
  height: 90vh;
  background-color: red;
  .container{
    .row{
      padding: 5rem 0;
      ul{
        list-style-type: none;
        display: flex;
        justify-content: space-between;
        text-align: center;
        li{

        }
      }
    }
  }
}
</style>
