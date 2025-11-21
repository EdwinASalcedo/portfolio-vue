<template>
  <div class="header-container">
    <HamburgerMenu />

    <router-link to="/">
      <img src="/icons/sslogo.png" alt="Logo" class="logo" />
    </router-link>

    <h1 class="page-title">{{ headerTitle }}</h1>

    <DarkModeToggle class="dark-mode-btn" />
  </div>
</template>

<script>
import DarkModeToggle from './DarkModeToggle.vue'
import HamburgerMenu from './HamburgerMenu.vue'

export default {
  name: 'Header',
  components: {
    HamburgerMenu,
    DarkModeToggle,
  },
  props: {
    headerTitle: {
      type: String,
      required: true,
    },
  },
}
</script>

<style scoped>
.header-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 1rem 1rem; /* This gives you top/bottom and side spacing */

  display: flex;
  flex-direction: column;
  align-items: center;

  position: relative; /* So we can position hamburger absolutely */
}

.header-container a {
  text-decoration: none;
  cursor: pointer;
}

.logo {
  width: 400px;
  height: auto;
}

.page-title {
  color: var(--text-primary);
  font-size: 3rem;
  margin-top: 1rem;
  margin-bottom: 0rem;
}

.dark-mode-btn {
  position: absolute;
  top: 1rem;
  left: 1rem;
}
</style>
