<script setup>
import { ref } from 'vue'

const email = ref('')
const password = ref('')
const rememberMe = ref(false)

const handleLogin = () => {
  console.log({ email: email.value, password: password.value, rememberMe: rememberMe.value })
}
</script>

<template>
  <div class="login-page">
    <div class="login-container">
      
      <div class="login-header">
        <div class="logo-group">
          <img :src="viteLogo" class="logo vite-logo" alt="Vite logo" />
          <span class="logo-divider">+</span>
          <img :src="vueLogo" class="logo vue-logo" alt="Vue logo" />
        </div>
        <h2 class="title">Welcome back</h2>
        <p class="subtitle">Sign in to access your dashboard</p>
      </div>

      <div class="login-card">
        <form class="login-form" @submit.prevent="handleLogin">
          
          <div class="form-group">
            <label for="email" class="form-label">Email address</label>
            <input
              id="email"
              v-model="email"
              name="email"
              type="email"
              autocomplete="email"
              required
              class="form-input"
              placeholder="you@example.com"
            />
          </div>

          <div class="form-group">
            <div class="label-row">
              <label for="password" class="form-label">Password</label>
              <a href="#" class="forgot-link">Forgot password?</a>
            </div>
            <input
              id="password"
              v-model="password"
              name="password"
              type="password"
              autocomplete="current-password"
              required
              class="form-input"
              placeholder="••••••••"
            />
          </div>

          <div class="checkbox-group">
            <input
              id="remember-me"
              v-model="rememberMe"
              name="remember-me"
              type="checkbox"
              class="checkbox-input"
            />
            <label for="remember-me" class="checkbox-label">
              Remember me for 30 days
            </label>
          </div>

          <button type="submit" class="submit-btn">
            Sign in
          </button>
        </form>

        <div class="divider-container">
          <div class="divider-line"></div>
          <span class="divider-text">Or continue with</span>
        </div>

        <div class="social-grid">
          <a href="https://github.com/vitejs/vite" target="_blank" class="social-btn">
            <svg class="social-icon" role="presentation" aria-hidden="true">
              <use href="/icons.svg#github-icon"></use>
            </svg>
            <span>GitHub</span>
          </a>

          <a href="https://chat.vite.dev/" target="_blank" class="social-btn">
            <svg class="social-icon" role="presentation" aria-hidden="true">
              <use href="/icons.svg#discord-icon"></use>
            </svg>
            <span>Discord</span>
          </a>
        </div>
      </div>

      <p class="footer-text">
        Need help? Check the 
        <a href="https://vite.dev/" target="_blank" class="footer-link vite-link">Vite Docs</a> 
        or 
        <a href="https://vuejs.org/" target="_blank" class="footer-link vue-link">Vue Docs</a>
      </p>

    </div>
  </div>
</template>

<style scoped>
/* Main Page Layout */
.login-page {
  min-height: 100vh;
  background-color: #020617;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 3rem 1.5rem;
  font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, sans-serif;
  color: #f8fafc;
}

.login-container {
  width: 100%;
  max-width: 28rem;
}

/* Header Section */
.login-header {
  text-align: center;
  margin-bottom: 2rem;
}

.logo-group {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 0.75rem;
  margin-bottom: 1rem;
}

.logo {
  height: 2.5rem;
  width: auto;
}

.vite-logo {
  animation: pulse 2s cubic-bezier(0.4, 0, 0.6, 1) infinite;
}

.logo-divider {
  color: #475569;
  font-size: 1.5rem;
  font-weight: 300;
}

.title {
  font-size: 1.875rem;
  line-height: 2.25rem;
  font-weight: 700;
  color: #ffffff;
  letter-spacing: -0.025em;
  margin: 0;
}

.subtitle {
  margin-top: 0.5rem;
  font-size: 0.875rem;
  color: #94a3b8;
}

/* Card Container */
.login-card {
  background-color: #0f172a;
  border: 1px solid #1e293b;
  border-radius: 1rem;
  padding: 2rem;
  box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.25);
}

/* Form Styling */
.login-form {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

.form-group {
  display: flex;
  flex-direction: column;
}

.label-row {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.form-label {
  display: block;
  font-size: 0.875rem;
  font-weight: 500;
  color: #cbd5e1;
  margin-bottom: 0.5rem;
}

.forgot-link {
  font-size: 0.875rem;
  font-weight: 500;
  color: #818cf8;
  text-decoration: none;
  transition: color 0.2s ease;
}

.forgot-link:hover {
  color: #a5b4fc;
}

.form-input {
  width: 100%;
  box-sizing: border-box;
  border-radius: 0.5rem;
  border: 1px solid #334155;
  background-color: rgba(30, 41, 59, 0.6);
  padding: 0.625rem 0.875rem;
  color: #ffffff;
  font-size: 0.875rem;
  outline: none;
  transition: all 0.2s ease;
}

.form-input::placeholder {
  color: #64748b;
}

.form-input:focus {
  border-color: #6366f1;
  box-shadow: 0 0 0 2px rgba(99, 102, 241, 0.4);
}

/* Checkbox */
.checkbox-group {
  display: flex;
  align-items: center;
}

.checkbox-input {
  height: 1rem;
  width: 1rem;
  border-radius: 0.25rem;
  border: 1px solid #334155;
  background-color: #1e293b;
  accent-color: #4f46e5;
  cursor: pointer;
}

.checkbox-label {
  margin-left: 0.75rem;
  font-size: 0.875rem;
  color: #94a3b8;
  cursor: pointer;
}

/* Primary Button */
.submit-btn {
  width: 100%;
  display: flex;
  justify-content: center;
  padding: 0.625rem 0.75rem;
  background-color: #4f46e5;
  color: #ffffff;
  font-size: 0.875rem;
  font-weight: 600;
  border: none;
  border-radius: 0.5rem;
  cursor: pointer;
  box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
  transition: all 0.2s ease;
}

.submit-btn:hover {
  background-color: #6366f1;
}

.submit-btn:active {
  transform: scale(0.99);
}

/* Divider */
.divider-container {
  position: relative;
  margin-top: 2rem;
  display: flex;
  align-items: center;
  justify-content: center;
}

.divider-line {
  position: absolute;
  width: 100%;
  border-top: 1px solid #1e293b;
}

.divider-text {
  position: relative;
  background-color: #0f172a;
  padding: 0 0.75rem;
  font-size: 0.75rem;
  text-transform: uppercase;
  color: #64748b;
  font-weight: 500;
}

/* Social Login Grid */
.social-grid {
  margin-top: 1.5rem;
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  gap: 0.75rem;
}

.social-btn {
  display: inline-flex;
  width: 100%;
  justify-content: center;
  align-items: center;
  gap: 0.5rem;
  border-radius: 0.5rem;
  background-color: rgba(30, 41, 59, 0.8);
  padding: 0.625rem 1rem;
  font-size: 0.875rem;
  font-weight: 500;
  color: #cbd5e1;
  border: 1px solid rgba(51, 65, 85, 0.6);
  text-decoration: none;
  box-sizing: border-box;
  transition: all 0.2s ease;
}

.social-btn:hover {
  background-color: #1e293b;
  color: #ffffff;
}

.social-icon {
  height: 1.25rem;
  width: 1.25rem;
  fill: currentColor;
}

/* Footer Links */
.footer-text {
  margin-top: 2rem;
  text-align: center;
  font-size: 0.75rem;
  color: #64748b;
}

.footer-link {
  font-weight: 500;
  text-decoration: none;
}

.footer-link:hover {
  text-decoration: underline;
}

.vite-link {
  color: #818cf8;
}

.vue-link {
  color: #34d399;
}

/* Keyframes */
@keyframes pulse {
  0%, 100% {
    opacity: 1;
  }
  50% {
    opacity: 0.5;
  }
}
</style>