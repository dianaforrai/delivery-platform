<template>
    <div class="container-fluid login-container">
      <form class="main-form">
        <h1 class="text-center">Login</h1>
        <div class="mb-3">
          <label for="inputEmail" class="form-label">Email</label>
          <input v-model="email" type="email" class="form-control" id="inputEmail" required>
        </div>
        <div class="mb-3">
          <label for="inputPassword" class="form-label">Password</label>
          <input v-model="password" type="password" class="form-control" id="inputPassword" aria-describedby="pwHelp"
            required>
          <div id="pwHelp" class="form-text">We'll never share your password with anyone else.</div>
        </div>
        <button @click="login($event)" type="submit" class="btn btn-primary">Login</button>
        <p class="create-account-info">Don't have an account? <router-link to="/register">Register</router-link></p>
      </form>
      <div class="toast" role="alert" aria-live="assertive" aria-atomic="true" data-bs-autohide="true"
        :class="{ 'show': showToast }" style="position: absolute; top: 0; right: 0;">
        <div class="toast-header">
          <strong class="me-auto">Notification</strong>
          <button type="button" class="m1-2 mb-1 btn-close" @click="showToast = false"></button>
        </div>
        <div class="toast-body">
          {{ toastMessage }}
        </div>
      </div>
  
    </div>
  </template>
  <script>

  export default {
  name: 'Login',
  props: {
    msg: String
  },
  data() {
    return {
      email: '',
      password: '',
      showToast: false,
      toastMessage: ''
    };
  },
  methods: {
    login(event) {
        event.preventDefault();
    },
    
  }
}
</script>