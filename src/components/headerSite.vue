<template>
  <header>
    <nav class="navbar navbar-dark bg-dark justify-content-around">
      <div class="d-flex align-items-center">
        <img class="img-fluid" src="../assets/logo.png" alt="logo">
        <a class="navbar-brand text-danger">Netflix</a>
      </div>

      <div>
        <form class="form-inline d-flex">

          <input v-model="search" class="form-control mr-sm-2" type="search" placeholder="Search" aria-label="Search">

          <button @click.prevent="$emit('parentSearch', search)" class="btn btn-outline-success my-2 my-sm-0"
            type="submit">Search</button>
        </form>
      </div>

    </nav>
  </header>
</template>

<script>
export default {

  data() {
    return {
      // ! DA COLLEGARE CON IL PARENT SEARCH
      search: 'spider man',
    }
  },
  methods: {
  }
}
</script>

<style scoped lang="scss">
header {
  height: 10vh;

  nav {
    height: 100%;

    img {
      height: 5rem;
      margin-right: .5rem;
    }
  }

  form {
    input {
      background-color: black;
      border: black;
      color: white;
      
    }

    button {
      background-color: black;
      border: black;
      color: red;
    }
  }
}
</style>
