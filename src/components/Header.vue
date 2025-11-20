<template>
  <div class="header-container">
    <HamburgerMenu />

    <router-link to="/">
      <img src="../assets/uf.png" alt="Logo" class="logo" />
    </router-link>

    <h1 class="page-title">{{ headerTitle }}</h1>
  </div>
</template>

<script>
import HamburgerMenu from './HamburgerMenu.vue'

export default {
  name: 'Header',
  components: {
    HamburgerMenu,
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
  width: 200px;
  height: auto;
}

.page-title {
  color: black;
  font-size: 3rem;
  margin-top: 1rem;
  margin-bottom: 0rem;
}
</style>
