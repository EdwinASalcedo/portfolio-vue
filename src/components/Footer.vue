<template>
  <footer class="footer">
    <div class="footer-container">
      <button @click="scrollToTop" class="back-to-top">
        <ArrowUp />
      </button>

      <div class="social-icons">
        <a href="https://github.com/EdwinASalcedo" target="_blank">
          <img src="/icons/github.svg" alt="GitHub" class="icon" />
        </a>
        <a href="https://twitter.com/EdSauce_edo" target="_blank">
          <img src="/icons/x.svg" alt="Twitter" class="icon" />
        </a>
        <a href="https://linkedin.com/in/edwin-a-salcedo/" target="_blank">
          <img src="/icons/linkedin.svg" alt="LinkedIn" class="icon" />
        </a>
      </div>
    </div>
  </footer>
</template>

<script setup>
import { ArrowUp } from 'lucide-vue-next'
function scrollToTop() {
  window.scrollTo({ top: 0, behavior: 'smooth' })
}
</script>

<style scoped>
.footer {
  margin-top: 4rem;
  padding: 2rem 0;
}

.footer-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 1rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.back-to-top {
  background: none;
  border: none;
  font-size: 1rem;
  cursor: pointer;
  color: #333;
}

.back-to-top:hover {
  color: #4a90e2;
}

.social-icons {
  display: flex;
  gap: 1.5rem;
  color: var(--text-primary);
}

.icon {
  width: 24px;
  height: 24px;
  color: var(--text-primary);
}

.social-icons a:hover .icon {
  opacity: 0.7;
}
</style>
