<template>
  <h2>Login</h2>

  <input type="text" v-model="username" placeholder="Username" />
  <br />
  <input type="password" v-model="password" placeholder="Password" />
  <br />
  <button @click="login">Login</button>

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
    login() {
      const savedUser = localStorage.getItem('user')

      if (!savedUser) {
        this.message = 'No user registered'
        return
      }

      const user = JSON.parse(savedUser)

      if (user.username === this.username && user.password === this.password) {
        this.message = 'Login successful'
      } else {
        this.message = 'Invalid credentials'
      }
    }
  }
}
</script>
