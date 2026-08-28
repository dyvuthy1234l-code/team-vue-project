<script setup lang="ts">
import { ref } from 'vue'
import heroImg from '../assets/hero.png'
import viteLogo from '../assets/vite.svg'
import vueLogo from '../assets/vue.svg'

const count = ref(0)
</script>

<template>
  <section id="center">
    <div class="hero">
      <img :src="heroImg" class="base" width="170" height="179" alt="" />
      <img :src="vueLogo" class="framework" alt="Vue logo" />
      <img :src="viteLogo" class="vite" alt="Vite logo" />
    </div>
    <div>
      <h1>Get started</h1>
      <p>Edit <code>src/App.vue</code> and save to test <code>HMR</code></p>
    </div>
    <button type="button" class="counter" @click="count++">
      Count is {{ count }}
    </button>
  </section>

  <div class="ticks"></div>

  <section id="next-steps">
    <div id="docs">
      <svg class="icon" role="presentation" aria-hidden="true">
        <use href="/icons.svg#documentation-icon"></use>
      </svg>
      <h2>Documentation</h2>
      <p>Your questions, answered</p>
      <ul>
        <li>
          <a href="https://vite.dev/" target="_blank">
            <img class="logo" :src="viteLogo" alt="" />
            Explore Vite
          </a>
        </li>
        <li>
          <a href="https://vuejs.org/" target="_blank">
            <img class="button-icon" :src="vueLogo" alt="" />
            Learn more
          </a>
        </li>
      </ul>
    </div>
    <div id="social">
      <svg class="icon" role="presentation" aria-hidden="true">
        <use href="/icons.svg#social-icon"></use>
      </svg>
      <h2>Connect with us</h2>
      <p>Join the Vite community</p>
      <ul>
        <li>
          <a href="https://github.com/vitejs/vite" target="_blank">
            <svg class="button-icon" role="presentation" aria-hidden="true">
              <use href="/icons.svg#github-icon"></use>
            </svg>
            GitHub
          </a>
        </li>
        <li>
          <a href="https://chat.vite.dev/" target="_blank">
            <svg class="button-icon" role="presentation" aria-hidden="true">
              <use href="/icons.svg#discord-icon"></use>
            </svg>
            Discord
          </a>
        </li>
        <li>
          <a href="https://x.com/vite_js" target="_blank">
            <svg class="button-icon" role="presentation" aria-hidden="true">
              <use href="/icons.svg#x-icon"></use>
            </svg>
            X.com
          </a>
        </li>
        <li>
          <a href="https://bsky.app/profile/vite.dev" target="_blank">
            <svg class="button-icon" role="presentation" aria-hidden="true">
              <use href="/icons.svg#bluesky-icon"></use>
            </svg>
            Bluesky
          </a>
        </li>
      </ul>
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
