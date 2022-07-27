<template>
  <nav class="navbar navbar-expand-lg navbar-light bg-light">
    <div class="container-fluid">
      <a class="navbar-brand" href="#">Кулинарный блог</a>
      <div class="collapse navbar-collapse" >
        <ul class="navbar-nav me-auto mb-2 mb-lg-0">
          <li class="nav-item">
            <nuxt-link exact no-prefetch active-class="active" class="nav-link" aria-current="page" to="/"> Home</nuxt-link>
          </li>
          <li class="nav-item">
            <nuxt-link active-class="active" class="nav-link" to="/about">About </nuxt-link>
          </li>
          <li class="nav-item">
            <nuxt-link active-class="active" class="nav-link" to="/users">Users </nuxt-link>
          </li>
          <li class="nav-item" v-if="!hasToken">
            <nuxt-link active-class="active" class="nav-link" to="/login">Login </nuxt-link>
          </li>
          <li class="nav-item" v-else>
            <a @click.prevent="logout" href="#">Logout </a>
          </li>
        </ul>
        <form class="d-flex">
          <input class="form-control me-2" type="search" placeholder="Search" aria-label="Search">
          <button class="btn btn-outline-success" type="submit">Search</button>
        </form>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  name: "navbar",
  computed: {
    hasToken(){
      return this.$store.getters.hasToken
    }
  },
  methods: {
    logout() {
      this.$store.dispatch('logout')
      this.$router.push('/login')
    }
  }
}
</script>

<style scoped>

</style>
