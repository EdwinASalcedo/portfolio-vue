<template>
  <div class="hamburger-container">
    <button class="hamburger" @click="toggleMenu" :class="{ open: menuOpen }">
      <span></span>
      <span></span>
      <span></span>
    </button>

    <!-- Dropdown menu -->
    <nav class="menu" :class="{ open: menuOpen }">
      <router-link to="/" @click="closeMenu">Home</router-link>
      <router-link to="/about" @click="closeMenu">About</router-link>
      <router-link to="/projects" @click="closeMenu">Projects</router-link>
      <!-- <router-link to="/apps" @click="closeMenu">Apps</router-link> -->
      <router-link to="/contact" @click="closeMenu">Contact</router-link>
    </nav>
  </div>
</template>

<script>
export default {
  name: 'HamburgerMenu',
  data() {
    return {
      menuOpen: false,
    }
  },
  methods: {
    toggleMenu() {
      this.menuOpen = !this.menuOpen
    },
    closeMenu() {
      this.menuOpen = false
    },
  },
}
</script>

<style scoped>
.hamburger-container {
  position: absolute;
  top: 1rem;
  right: 1rem;
}

.hamburger {
  background: none;
  border: none;
  cursor: pointer;
  padding: 0.5rem;
  display: flex;
  flex-direction: column;
  gap: 5px;
  z-index: 1001;
}

.hamburger span {
  width: 30px;
  height: 3px;
  background: var(--text-primary);
  transition: all 0.3s ease;
  border-radius: 2px;
}

/* Hamburger animation to X */
.hamburger.open span:nth-child(1) {
  transform: rotate(45deg) translate(8px, 8px);
}

.hamburger.open span:nth-child(2) {
  opacity: 0;
}

.hamburger.open span:nth-child(3) {
  transform: rotate(-45deg) translate(8px, -8px);
}

/* Dropdown menu */
.menu {
  position: absolute;
  top: 100%;
  right: 0;
  margin-top: 0.5rem;
  background: var(--bg-secondary);
  border-radius: 8px;
  box-shadow: 0 4px 12px var(--card-shadow);
  display: flex;
  flex-direction: column;
  padding: 0.5rem 0;
  min-width: 200px;
  opacity: 0;
  visibility: hidden;
  transform: translateY(-10px);
  transition: all 0.3s ease;
  z-index: 1000;
}

.menu.open {
  opacity: 1;
  visibility: visible;
  transform: translateY(0);
}

.menu a {
  font-size: 1.1rem;
  color: var(--text-primary);
  text-decoration: none;
  padding: 0.75rem 1.5rem;
  transition: background 0.2s;
}

.menu a:hover {
  background: var(--hover-bg);
}

.menu a.router-link-active {
  /* color: #4a90e2; */
  background: #7d7d7d2d;
}
</style>
