<template>
  <div id="app"> 
    <headerSite @channelSearch="functionSearch" />
    <mainSite :search="searchInput" />
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
      searchInput:"",
    }
  },
  methods:{
    functionSearch(needle){
      console.warn(`this is needle ${needle}`);
      this.searchInput = needle;
      console.log(`this is search input ${searchInput}`);
    }
  }
}
</script>
 
<style lang="scss">
@import "~bootstrap/scss/bootstrap.scss";

</style>
