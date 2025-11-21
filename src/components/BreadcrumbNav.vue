<template>
  <nav class="breadcrumb" v-if="breadcrumbs.length > 1">
    <div
      v-for="(crumb, index) in breadcrumbs"
      :key="index"
      class="breadcrumb-item"
      :class="{ active: index === breadcrumbs.length - 1 }"
      @click="navigate(crumb.path, index)"
    >
      <span class="crumb-content">
        {{ crumb.name }}
      </span>
    </div>
  </nav>
</template>

<script>
export default {
  name: 'BreadcrumbNav',
  computed: {
    breadcrumbs() {
      const route = this.$route
      const pathArray = route.path.split('/').filter((p) => p)

      const crumbs = [{ name: 'Home', path: '/' }]

      let currentPath = ''
      pathArray.forEach((segment) => {
        currentPath += `/${segment}`
        const name = segment.charAt(0).toUpperCase() + segment.slice(1)
        crumbs.push({ name, path: currentPath })
      })

      return crumbs
    },
  },
  methods: {
    navigate(path, index) {
      // Don't navigate if it's the last item (current page)
      if (index !== this.breadcrumbs.length - 1) {
        this.$router.push(path)
      }
    },
  },
}
</script>

<style scoped>
.breadcrumb {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0rem 1rem 1rem;
  display: flex;
  gap: 0;
}

.breadcrumb-item {
  position: relative;
  background: #e8e8e8;
  padding: 0.75rem 2rem 0.75rem 1.5rem;
  cursor: pointer;
  transition: background 0.2s;
  display: flex;
  align-items: center;
}

/* First item - rounded left */
.breadcrumb-item:first-child {
  border-radius: 8px 0 0 8px;
  padding-left: 1rem;
}

/* Last item - rounded right, no arrow */
.breadcrumb-item:last-child {
  border-radius: 0 8px 8px 0;
  padding-right: 1rem;
}

/* Arrow shape using pseudo-element */
.breadcrumb-item:not(:last-child)::after {
  content: '';
  position: absolute;
  right: -10px;
  top: 0;
  width: 0;
  height: 0;
  border-top: 22px solid transparent;
  border-bottom: 22px solid transparent;
  border-left: 10px solid #e8e8e8;
  z-index: 2;
}

/* Active/current item styling */
.breadcrumb-item.active {
  background: #d0d0d0;
  cursor: default;
}

.breadcrumb-item.active::after {
  border-left-color: #d0d0d0;
}

/* Hover effect (except active) */
.breadcrumb-item:not(.active):hover {
  background: #d8d8d8;
}

.breadcrumb-item:not(.active):hover::after {
  border-left-color: #d8d8d8;
}

.crumb-content {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  font-size: 0.95rem;
  color: #333;
  font-weight: 500;
  white-space: nowrap;
}

.icon {
  font-size: 1rem;
}
</style>
