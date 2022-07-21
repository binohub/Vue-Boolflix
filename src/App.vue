<template>
  <div id="app"> 
    <headerSite />
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
  }
  data: function(){
    
  }
}
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap.scss";

</style>
