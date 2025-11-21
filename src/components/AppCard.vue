<template>
  <div class="app-card">
    <img :src="icon" :alt="title" class="app-icon" />

    <div class="app-info">
      <h4 class="app-title">{{ title }}</h4>
      <p class="app-subtitle">{{ subtitle }}</p>
      <button class="view-button" @click="handleClick">View</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'AppCard',
  props: {
    icon: {
      type: String,
      required: true,
    },
    title: {
      type: String,
      required: true,
    },
    subtitle: {
      type: String,
      required: true,
    },
    to: {
      type: String,
      required: false,
    },
    external: {
      type: Boolean,
      default: false,
    },
  },
  methods: {
    handleClick() {
      if (this.external) {
        window.open(this.to, '_blank')
      } else if (this.to) {
        this.$router.push(this.to)
      }
    },
  },
}
</script>

<style scoped>
.app-card {
  display: flex;
  align-items: center;
  gap: 1rem;
  padding: 1rem;
}

.app-icon {
  width: 96px;
  height: 96x;
  border-radius: 24px;
  flex-shrink: 0;
}

.app-info {
  flex: 1;
  min-width: 0; /* Allows text to truncate */
}

.app-title {
  font-size: 1rem;
  font-weight: 600;
  margin: 0 0 0.25rem 0;
  color: var(--text-primary);
}

.app-subtitle {
  font-size: 0.875rem;
  color: var(--text-secondary);
  margin: 0 0 0.5rem 0;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}

.view-button {
  background: #007aff;
  color: white;
  border: none;
  border-radius: 20px;
  padding: 0.5rem 1rem;
  font-size: 0.875rem;
  font-weight: 600;
  cursor: pointer;
  flex-shrink: 0;
}

.view-button:hover {
  background: #0051d5;
}
</style>
