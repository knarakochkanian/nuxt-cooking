<template>
<section>
  <h1>Users Page</h1>
  <ul  v-for="user in users" :key="user.id">
    <li>
      <a href="#" @click.prevent="openUser(user)"> {{user.name}}</a>
    </li>
  </ul>
</section>
</template>

<script>
export default {
  name: "index",
async fetch ({store}){
    if (store.getters['users/users'].length === 0 ) {
      await store.dispatch('users/fetch')
    }
},
  data: ()=>({}),
  computed: {
    users(){
      return this.$store.getters['users/users']
    }
  },
  methods:{
    openUser(user){
      this.$router.push('/users/' + user.id)
    }
  }
}
</script>

<style scoped>

</style>
