<template>
  <section>
    <h1>Login Page</h1>
    <form @submit.prevent="onSubmit">
      <div class="form-group">
        <input type="text" class="form-control">
      </div>
    </form>
    <p>
      <nuxt-link to="/">Home Page</nuxt-link>
    </p>
    <button class="btn btn-primary" type="submit"> Login</button>
  </section>

</template>

<script>
export default {
  name: "Login",
  layout: 'empty',
  methods: {
    onSubmit(){
      this.$store.dispatch('login')
      this.$router.push('/')
    }
  }
}
</script>

<style scoped>

section{
  width: 500px;
  margin: 0 auto;
  margin-top: 50px;

}
</style>
