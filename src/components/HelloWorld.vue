
```vue
<script setup lang="ts">
import { ref } from 'vue'

const email = ref('')
const password = ref('')
const rememberMe = ref(false)

const handleLogin = () => {
  console.log({
    email: email.value,
    password: password.value,
    rememberMe: rememberMe.value,
  })
}
</script>

<template>
  <div class="login-page">
    <div class="login-card">

      <!-- Logo / Brand -->
      <div class="brand">
        <div class="brand-icon">V</div>
        <h1>Welcome Back</h1>
        <p>Sign in to your account</p>
      </div>

      <!-- Login Form -->
      <form @submit.prevent="handleLogin">

        <!-- Email -->
        <div class="form-group">
          <label for="email">Email Address</label>
          <input
            id="email"
            v-model="email"
            type="email"
            placeholder="Enter your email"
            required
          />
        </div>

        <!-- Password -->
        <div class="form-group">
          <label for="password">Password</label>
          <input
            id="password"
            v-model="password"
            type="password"
            placeholder="Enter your password"
            required
          />
        </div>

        <!-- Options -->
        <div class="form-options">
          <label class="remember">
            <input
              v-model="rememberMe"
              type="checkbox"
            />
            <span>Remember me</span>
          </label>

          <a href="#">Forgot Password?</a>
        </div>

        <!-- Login Button -->
        <button type="submit" class="login-btn">
          Sign In
        </button>

      </form>

      <!-- Register -->
      <div class="register">
        Don't have an account?
        <a href="#">Create Account</a>
      </div>

    </div>
  </div>
</template>

<style scoped>
* {
  box-sizing: border-box;
}

.login-page {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 20px;
  background: linear-gradient(135deg, #eef2ff, #f8fafc);
  font-family: Arial, sans-serif;
}

.login-card {
  width: 100%;
  max-width: 420px;
  padding: 40px;
  background: #ffffff;
  border-radius: 20px;
  box-shadow: 0 20px 50px rgba(0, 0, 0, 0.08);
}

/* Brand */
.brand {
  text-align: center;
  margin-bottom: 30px;
}

.brand-icon {
  width: 55px;
  height: 55px;
  margin: 0 auto 15px;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 14px;
  background: #42b883;
  color: white;
  font-size: 25px;
  font-weight: bold;
}

.brand h1 {
  margin: 0;
  color: #1e293b;
  font-size: 28px;
}

.brand p {
  margin-top: 8px;
  color: #64748b;
  font-size: 14px;
}

/* Form */
.form-group {
  margin-bottom: 20px;
}

.form-group label {
  display: block;
  margin-bottom: 8px;
  color: #334155;
  font-size: 14px;
  font-weight: 600;
}

.form-group input {
  width: 100%;
  padding: 13px 15px;
  border: 1px solid #cbd5e1;
  border-radius: 10px;
  outline: none;
  font-size: 14px;
  transition: 0.2s;
}

.form-group input:focus {
  border-color: #42b883;
  box-shadow: 0 0 0 3px rgba(66, 184, 131, 0.12);
}

/* Options */
.form-options {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin: 5px 0 25px;
  font-size: 13px;
}

.remember {
  display: flex;
  align-items: center;
  gap: 7px;
  color: #64748b;
}

.remember input {
  accent-color: #42b883;
}

.form-options a,
.register a {
  color: #42b883;
  text-decoration: none;
  font-weight: 600;
}

/* Button */
.login-btn {
  width: 100%;
  padding: 14px;
  border: none;
  border-radius: 10px;
  background: #42b883;
  color: white;
  font-size: 15px;
  font-weight: 600;
  cursor: pointer;
  transition: 0.2s;
}

.login-btn:hover {
  background: #35a774;
  transform: translateY(-1px);
}

/* Register */
.register {
  margin-top: 25px;
  text-align: center;
  color: #64748b;
  font-size: 13px;
}
</style>
```
