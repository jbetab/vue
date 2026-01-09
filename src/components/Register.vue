<template>
  <h2>Register</h2>

  <input type="text" v-model="username" placeholder="Username" />
  <br />
  <input type="password" v-model="password" placeholder="Password" />
  <br />
  <button @click="register">Register</button>

  <p>{{ message }}</p>
</template>

<script lang="ts">
export default {
  data() {
    return {
      username: '',
      password: '',
      message: ''
    }
  },
  methods: {
    register() {
      if (this.username === '' || this.password === '') {
        this.message = 'Fill all fields'
        return
      }

      const user = {
        username: this.username,
        password: this.password
      }

      localStorage.setItem('user', JSON.stringify(user))
      this.message = 'User registered successfully'
    }
  }
}
</script>
