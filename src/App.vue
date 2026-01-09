<template>
  <h1>Basic Auth</h1>

  <Register />
  <hr />
  <Login />
</template>

<script lang="ts">
import Register from './components/Register.vue'
import Login from './components/Login.vue'

export default {
  components: {
    Register,
    Login
  }
}
</script>









