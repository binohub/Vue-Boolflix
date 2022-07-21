<template>
  <div id="app"> 

    <headerSite @channelSearch="functionSearch"  />
    <mainSite />

  </div>
</template>

<script>
import headerSite from './components/headerSite.vue'
import mainSite from './components/mainSite.vue'

export default {
  name: 'App',
  components: {
    headerSite,
    mainSite,
  },
  data: function(){
    return{
      search:'',
    }
  },
  methods:{
    functionSearch(input){
      this.search = input;
      console.log(`this is search ${this.search}`);
    }
  }
}
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap.scss";

</style>
