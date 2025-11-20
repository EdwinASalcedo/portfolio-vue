<template>
  <div class="card-wrapper" @click="handleClick">
    <div class="card" :style="{ borderTopColor: color }">
      <div class="card-front">
        <img v-if="isImagePath" :src="icon" class="icon-img" />
        <span v-else class="icon">{{ icon }}</span>
        <h3>{{ title }}</h3>
      </div>
      <div class="card-back" :style="{ backgroundColor: lighterColor }">
        <h3>{{ title }}</h3>
        <p>{{ subtitle }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Card',
  props: {
    icon: {
      type: [String],
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
    color: {
      type: String,
      default: '#333',
    },
    to: { type: String, required: false },
    external: { type: Boolean, default: false },
  },
  computed: {
    isImagePath() {
      const result = typeof this.icon === 'string' && this.icon.startsWith('/')
      console.log('Icon value:', this.icon)
      console.log('Is image path?', result)
      return result
    },
    lighterColor() {
      // Convert hex to RGB
      const hex = this.color.replace('#', '')
      const r = parseInt(hex.substring(0, 2), 16)
      const g = parseInt(hex.substring(2, 4), 16)
      const b = parseInt(hex.substring(4, 6), 16)

      // Mix with white (increase RGB values towards 255)
      const mixAmount = 0.85 // 85% white mixed in (adjust for lighter/darker)
      const newR = Math.round(r + (255 - r) * mixAmount)
      const newG = Math.round(g + (255 - g) * mixAmount)
      const newB = Math.round(b + (255 - b) * mixAmount)

      return `rgb(${newR}, ${newG}, ${newB})`
    },
  },
  methods: {
    handleClick() {
      if (this.external) {
        console.log('Opening external link')
        window.open(this.to, '_blank')
      } else {
        console.log('Internal navigation')
        this.$router.push(this.to)
      }
    },
  },
}
</script>

<style scoped>
.card-wrapper {
  perspective: 1000px;
  height: 200px;
}

.card {
  background: white;
  border-top: 6px solid #333;
  padding: 0;
  text-align: center;
  cursor: pointer;
  transition: transform 0.6s;
  transform-style: preserve-3d;
  position: relative;
  width: 100%;
  height: 100%;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.5);
}

.card-wrapper:hover .card {
  transform: rotateY(180deg) translateY(-10px);
}

.icon {
  font-size: 3rem;
  display: block;
  margin-bottom: 1rem;
}

.icon-img {
  width: 96px;
  height: 96px;
  margin-bottom: 1rem;
  object-fit: contain;
}

.card-front,
.card-back {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  backface-visibility: hidden;
  padding: 2rem 1rem;
}

.card-front {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.card-back {
  transform: rotateY(180deg);
  text-align: left;
}

.card h3 {
  font-size: 1.2rem;
}

.card-back p {
  font-size: 1.2rem;
  color: #666;
}

.icon-component {
  margin-bottom: 1rem;
}
</style>
