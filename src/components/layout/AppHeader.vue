<template>
  <div>
    <b-nav justified>
      <b-nav-item active><router-link to="/">Home</router-link></b-nav-item>
      <b-nav-item ><router-link to="/usuarios">Usuarios</router-link></b-nav-item>
      <b-nav-item ><router-link to="/login">Login</router-link></b-nav-item>
    </b-nav>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
div{
  background-color: rgb(127, 183, 197);
}
</style>
