<!-- LoginPage.vue -->
<template>
    <div class="login-container">
      <div class="login-card">
        <!-- Left Section -->
        <div class="welcome-section">
          <h1>Welcome to ...</h1>
          <p>Your Complete School Management Solution.</p>
        </div>
        
        <!-- Right Section -->
        <div class="login-section">
          <h2>USER LOGIN</h2>
          <form @submit.prevent="handleSubmit">
            <div class="form-group">
              <div class="input-with-icon">
                <i class="fas fa-user"></i>
                <input type="text" v-model="username" placeholder="Username" required>
              </div>
            </div>
            <div class="form-group">
              <div class="input-with-icon">
                <i class="fas fa-lock"></i>
                <input type="password" v-model="password" placeholder="Password" required>
              </div>
            </div>
            <div class="form-group remember">
              <label>
                <input type="checkbox" v-model="remember">
                <span>Remember me</span>
              </label>
              <a href="#" class="forgot-password">Forgot password?</a>
            </div>
            <button type="submit" class="login-btn">LOGIN</button>
          </form>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'LoginPage',
    data() {
      return {
        username: '',
        password: '',
        remember: false
      }
    },
    methods: {
      handleSubmit() {
        console.log('Login attempted:', {
          username: this.username,
          password: this.password,
          remember: this.remember
        })
      }
    }
  }
  </script>
  
  <style scoped>
  .login-container {
    width: 100vw;
    height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    background: linear-gradient(135deg, #6c5ce7 0%, #a166ab 100%);
    margin: 0;
    padding: 40px;
    overflow: hidden;
    position: fixed;
    top: 0;
    left: 0;
  }
  
  .login-card {
    display: flex;
    background: white;
    width: 90%;
    max-width: 1200px;
    min-height: 600px;
    border-radius: 20px;
    box-shadow: 0 15px 30px rgba(0, 0, 0, 0.2);
    overflow: hidden;
  }
  
  .welcome-section {
    background: linear-gradient(135deg, #8b5cf6 0%, #d946ef 100%);
    color: white;
    padding: 60px;
    flex: 1.6;
    display: flex;
    flex-direction: column;
    justify-content: center;
  }
  
  .welcome-section h1 {
    font-size: 2.8rem;
    margin-bottom: 30px;
    font-weight: 600;
  }
  
  .welcome-section p {
    font-size: 1.1rem;
    line-height: 1.6;
    opacity: 0.9;
  }
  
  .login-section {
    padding: 60px 40px;
    flex: 1;
    background: white;
    display: flex;
    flex-direction: column;
    justify-content: center;
  }
  
  .login-section h2 {
    color: #8b5cf6;
    margin-bottom: 40px;
    font-size: 1.8rem;
    text-align: center;
    font-weight: 700;
  }
  
  .form-group {
    margin-bottom: 25px;
  }
  
  .input-with-icon {
    position: relative;
  }
  
  .input-with-icon i {
    position: absolute;
    left: 14px;
    top: 50%;
    transform: translateY(-50%);
    color: #8b5cf6;
    font-size: 1.1rem;
  }
  
  input[type="text"],
  input[type="password"] {
    width: 100%;
    padding: 14px;
    padding-left: 40px;
    border: 1px solid #ddd;
    border-radius: 8px;
    font-size: 1rem;
    transition: border-color 0.3s ease;
  }
  
  input[type="text"]:focus,
  input[type="password"]:focus {
    border-color: #8b5cf6;
    outline: none;
  }
  
  .remember {
    display: flex;
    justify-content: space-between;
    align-items: center;
    font-size: 0.9rem;
    margin-bottom: 30px;
  }
  
  .login-btn {
    width: 100%;
    padding: 14px;
    background: #8b5cf6;
    color: white;
    border: none;
    border-radius: 8px;
    font-size: 1rem;
    cursor: pointer;
    transition: background 0.3s ease;
    font-weight: 600;
  }
  
  .login-btn:hover {
    background: #7c3aed;
  }
  
  .forgot-password {
    color: #8b5cf6;
    text-decoration: none;
  }
  
  @media (max-width: 968px) {
    .login-container {
      padding: 20px;
    }
    
    .login-card {
      width: 95%;
      flex-direction: column;
    }
    
    .welcome-section,
    .login-section {
      padding: 40px 30px;
      flex: none;
    }
    
    .welcome-section h1 {
      font-size: 2rem;
    }
  }
  </style>