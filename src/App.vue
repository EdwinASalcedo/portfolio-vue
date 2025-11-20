<script setup>
import Header from './components/Header.vue'
import Footer from './components/Footer.vue'
</script>

<template>
  <div id="app">
    <!-- <Header></Header> -->
    <router-view></router-view>
    <Footer></Footer>
  </div>
</template>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  margin: 0;
  padding: 0;
  font-family: -apple-system, BlinkMacSystemFont, 'SF Pro', 'Segoe UI', Arial, sans-serif;
}

#app {
  width: 100%;
  font-family: -apple-system, BlinkMacSystemFont, 'SF Pro', 'Segoe UI', Arial, sans-serif;
}
</style>
