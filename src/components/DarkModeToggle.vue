<template>
  <button @click="toggleDarkMode" class="dark-mode-toggle" aria-label="Toggle dark mode">
    <span v-if="isDark">☀️</span>
    <span v-else>🌙</span>
  </button>
</template>

<script>
export default {
  name: 'DarkModeToggle',
  data() {
    return {
      isDark: false,
    }
  },
  mounted() {
    // Check for saved preference or system preference
    const savedTheme = localStorage.getItem('theme')
    const prefersDark = window.matchMedia('(prefers-color-scheme: dark)').matches

    this.isDark = savedTheme === 'dark' || (!savedTheme && prefersDark)
    this.applyTheme()
  },
  methods: {
    toggleDarkMode() {
      this.isDark = !this.isDark
      this.applyTheme()
      localStorage.setItem('theme', this.isDark ? 'dark' : 'light')
    },
    applyTheme() {
      if (this.isDark) {
        document.documentElement.classList.add('dark')
      } else {
        document.documentElement.classList.remove('dark')
      }
    },
  },
}
</script>

<style scoped>
.dark-mode-toggle {
  background: none;
  border: none;
  font-size: 1.5rem;
  cursor: pointer;
  padding: 0.5rem;
  transition: transform 0.2s;
}

.dark-mode-toggle:hover {
  transform: scale(1.1);
}
</style>
