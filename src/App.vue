<script setup>
import Header from './components/Header.vue'
import Footer from './components/Footer.vue'
</script>

<template>
  <div id="app">
    <!-- <Header></Header> -->
    <!-- <router-view></router-view> -->
    <main class="main-content">
      <router-view></router-view>
    </main>
    <Footer></Footer>
  </div>
</template>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

/* CSS Variables for light mode (default) */
:root {
  --bg-primary: #f8f9fa;
  --bg-secondary: #fafaf9;
  --bg-tertiary: #f5f5f5;
  --text-primary: #333333;
  --text-secondary: #666666;
  --text-tertiary: #999999;
  --border-color: #e0e0e0;
  --card-shadow: rgba(0, 0, 0, 0.5);
  --hover-bg: #f5f5f5;
}

/* Dark mode variables */
.dark {
  --bg-primary: #1a1a1a;
  --bg-secondary: #2a2a2a;
  --bg-tertiary: #3a3a3a;
  --text-primary: #e0e0e0;
  --text-secondary: #b0b0b0;
  --text-tertiary: #888888;
  --border-color: #3a3a3a;
  --card-shadow: rgba(0, 0, 0, 0.7);
  --hover-bg: #3a3a3a;
}

body {
  margin: 0;
  padding: 0;
  font-family: -apple-system, BlinkMacSystemFont, 'SF Pro', 'Segoe UI', Arial, sans-serif;
  background-color: var(--bg-primary);
  color: var(--text-primary);
  transition:
    background-color 0.3s ease,
    color 0.3s ease;
}

#app {
  width: 100%;
  font-family: -apple-system, BlinkMacSystemFont, 'SF Pro', 'Segoe UI', Arial, sans-serif;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}

.main-content {
  flex: 1; /* Takes up all available space */
}

h1,
h2,
h3,
h4,
h5,
h6 {
  color: var(--text-primary);
}

p {
  color: var(--text-secondary);
}
</style>
