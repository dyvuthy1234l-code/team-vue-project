<script setup lang="ts">
import { ref, reactive } from 'vue'

const isSubmitting = ref(false)
const showPassword = ref(false)

const form = reactive({
  email: '',
  password: '',
  rememberMe: false,
})

const handleLogin = async () => {
  isSubmitting.value = true
  try {
    // Perform authentication request here
    console.log('Logging in with:', form)
    await new Promise((resolve) => setTimeout(resolve, 1000))
  } finally {
    isSubmitting.value = false
  }
}
</script>

<template>
  <div class="login-wrapper">
    <div class="login-card">
      <div class="login-header">
        <div class="brand-logo">
          <svg viewBox="0 0 24 24" width="32" height="32" fill="none" stroke="currentColor" stroke-width="2">
            <path d="M12 2L2 7l10 5 10-5-10-5zM2 17l10 5 10-5M2 12l10 5 10-5" />
          </svg>
        </div>
        <h1>Welcome back</h1>
        <p>Please enter your details to sign in</p>
      </div>

      <form @submit.prevent="handleLogin" class="login-form">
        <div class="form-group">
          <label for="email">Email address</label>
          <input
            id="email"
            v-model="form.email"
            type="email"
            placeholder="name@company.com"
            required
            autocomplete="email"
          />
        </div>

        <div class="form-group">
          <div class="label-row">
            <label for="password">Password</label>
            <a href="#" class="forgot-link">Forgot password?</a>
          </div>
          <div class="input-relative">
            <input
              id="password"
              v-model="form.password"
              :type="showPassword ? 'text' : 'password'"
              placeholder="••••••••"
              required
              autocomplete="current-password"
            />
            <button
              type="button"
              class="toggle-password"
              @click="showPassword = !showPassword"
              :aria-label="showPassword ? 'Hide password' : 'Show password'"
            >
              {{ showPassword ? 'Hide' : 'Show' }}
            </button>
          </div>
        </div>

        <div class="form-actions">
          <label class="checkbox-label">
            <input type="checkbox" v-model="form.rememberMe" />
            <span>Remember for 30 days</span>
          </label>
        </div>

        <button type="submit" class="submit-btn" :disabled="isSubmitting">
          <span v-if="!isSubmitting">Sign In</span>
          <span v-else class="loader"></span>
        </button>
      </form>

      <div class="divider">
        <span>Or continue with</span>
      </div>

      <div class="social-login">
        <button type="button" class="social-btn">
          <svg viewBox="0 0 24 24" width="18" height="18"><path fill="currentColor" d="M12 2A10 10 0 0 0 2 12c0 4.42 2.87 8.17 6.84 9.5c.5.08.66-.23.66-.5v-1.69c-2.77.6-3.36-1.34-3.36-1.34c-.46-1.16-1.11-1.47-1.11-1.47c-.91-.62.07-.6.07-.6c1 .07 1.53 1.03 1.53 1.03c.87 1.52 2.34 1.07 2.91.83c.09-.65.35-1.09.63-1.34c-2.22-.25-4.55-1.11-4.55-4.92c0-1.11.38-2 1.03-2.71c-.1-.25-.45-1.29.1-2.64c0 0 .84-.27 2.75 1.02c.79-.22 1.65-.33 2.5-.33c.85 0 1.71.11 2.5.33c1.91-1.29 2.75-1.02 2.75-1.02c.55 1.35.2 2.39.1 2.64c.65.71 1.03 1.6 1.03 2.71c0 3.82-2.34 4.66-4.57 4.91c.36.31.69.92.69 1.85V21c0 .27.16.59.67.5C19.14 20.16 22 16.42 22 12A10 10 0 0 0 12 2Z"/></svg>
          GitHub
        </button>
      </div>

      <p class="signup-prompt">
        Don't have an account? <a href="#">Sign up</a>
      </p>
    </div>
  </div>
</template>

<style scoped>
.login-wrapper {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  background-color: #f8fafc;
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
  color: #0f172a;
}

.login-card {
  width: 100%;
  max-width: 400px;
  padding: 2.5rem;
  background: #ffffff;
  border-radius: 12px;
  box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.05), 0 4px 6px -2px rgba(0, 0, 0, 0.025);
  border: 1px solid #e2e8f0;
}

.login-header {
  text-align: center;
  margin-bottom: 2rem;
}

.brand-logo {
  color: #4f46e5;
  margin-bottom: 1rem;
}

.login-header h1 {
  font-size: 1.5rem;
  font-weight: 700;
  margin: 0 0 0.5rem;
}

.login-header p {
  color: #64748b;
  font-size: 0.875rem;
  margin: 0;
}

.login-form {
  display: flex;
  flex-direction: column;
  gap: 1.25rem;
}

.form-group {
  display: flex;
  flex-direction: column;
  gap: 0.375rem;
}

.label-row {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

label {
  font-size: 0.875rem;
  font-weight: 500;
}

.forgot-link, .signup-prompt a {
  color: #4f46e5;
  font-size: 0.875rem;
  text-decoration: none;
  font-weight: 500;
}

.forgot-link:hover, .signup-prompt a:hover {
  text-decoration: underline;
}

.input-relative {
  position: relative;
}

input[type="email"],
input[type="password"],
input[type="text"] {
  width: 100%;
  padding: 0.625rem 0.875rem;
  border: 1px solid #cbd5e1;
  border-radius: 6px;
  font-size: 0.875rem;
  box-sizing: border-box;
  transition: border-color 0.2s, box-shadow 0.2s;
}

input:focus {
  outline: none;
  border-color: #4f46e5;
  box-shadow: 0 0 0 3px rgba(79, 70, 229, 0.1);
}

.toggle-password {
  position: absolute;
  right: 0.75rem;
  top: 50%;
  transform: translateY(-50%);
  background: none;
  border: none;
  color: #64748b;
  font-size: 0.75rem;
  cursor: pointer;
}

.form-actions {
  display: flex;
  align-items: center;
}

.checkbox-label {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  font-size: 0.875rem;
  color: #475569;
  cursor: pointer;
}

.submit-btn {
  width: 100%;
  padding: 0.625rem;
  background-color: #4f46e5;
  color: white;
  border: none;
  border-radius: 6px;
  font-weight: 600;
  font-size: 0.875rem;
  cursor: pointer;
  transition: background-color 0.2s;
  display: flex;
  justify-content: center;
  align-items: center;
}

.submit-btn:hover {
  background-color: #4338ca;
}

.submit-btn:disabled {
  opacity: 0.7;
  cursor: not-allowed;
}

.divider {
  display: flex;
  align-items: center;
  text-align: center;
  margin: 1.5rem 0;
  color: #94a3b8;
  font-size: 0.75rem;
}

.divider::before,
.divider::after {
  content: '';
  flex: 1;
  border-bottom: 1px solid #e2e8f0;
}

.divider span {
  padding: 0 0.5rem;
}

.social-btn {
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 0.5rem;
  padding: 0.625rem;
  background: white;
  border: 1px solid #cbd5e1;
  border-radius: 6px;
  font-size: 0.875rem;
  font-weight: 500;
  cursor: pointer;
}

.social-btn:hover {
  background-color: #f8fafc;
}

.signup-prompt {
  text-align: center;
  font-size: 0.875rem;
  color: #64748b;
  margin-top: 1.5rem;
  margin-bottom: 0;
}

.loader {
  width: 16px;
  height: 16px;
  border: 2px solid #ffffff;
  border-bottom-color: transparent;
  border-radius: 50%;
  display: inline-block;
  animation: rotation 1s linear infinite;
}

@keyframes rotation {
  0% { transform: rotate(0deg); }
  100% { transform: rotate(360deg); }
}
</style>
