<!-- LoginPage.vue -->
<template>
  <div class="login-container">
    <div class="animated-background background-move"></div>
    <div class="login-card fade-in-up">

      <!-- Left Section -->
      <div class="welcome-section slide-in-left">
        <h1>Welcome to ...</h1>
        <p>Your Complete School Management Solution.</p>
      </div>

      <!-- Right Section -->
      <div class="login-section slide-in-right">
        <h2>USER LOGIN</h2>
        <form @submit.prevent="handleSubmit">
          <div class="form-group">
            <div class="input-with-icon">
              <i class="fa-solid fa-user"></i>
              <input type="text" v-model="username" placeholder="Username" required class="input-animate">
            </div>
          </div>
          <div class="form-group">
            <div class="input-with-icon">
              <i class="fa-solid fa-lock"></i>
              <input type="password" v-model="password" placeholder="Password" required class="input-animate">
            </div>
          </div>
          <div class="form-group remember fade-in">
            <label>
              <input type="checkbox" v-model="remember">
              <span>Remember me</span>
            </label>
            <a href="#" class="forgot-password fade-in">Forgot password?</a>
          </div>
          <button type="submit" class="login-btn scale-in">LOGIN</button>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
import '@/assets/media.css'

export default {
  name: 'LoginPage',
  data() {
    return {
      username: '',
      password: '',
      remember: false
    }
  },
  mounted() {
    this.animateBackground();
  },
  methods: {
    handleSubmit() {
      console.log('Login attempted:', {
        username: this.username,
        password: this.password,
        remember: this.remember
      })
    },
    animateBackground() {
      const bg = document.querySelector('.animated-background');
      if (bg) {
        bg.classList.add('background-move');
      }
    }
  }
}
</script>
