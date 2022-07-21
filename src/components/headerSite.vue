<template>
  <header>
    <input type="text" placeholder="ricerca"
    v-model="search" @keyup.enter="$emit('channelSearch', this.search)">
  </header>
</template>

<script>
export default {

  data(){
    return{
      search:'',
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
header {
  height: 10vh;
}
</style>
