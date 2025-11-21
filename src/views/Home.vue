<script setup>
import Card from '@/components/Card.vue'
import Header from '@/components/Header.vue'
import AppCard from '@/components/AppCard.vue'
import { Send } from 'lucide-vue-next'
</script>

<template>
  <Header headerTitle="Home"></Header>
  <div class="home">
    <section class="hero">
      <p class="hero-text">
        My name is Edwin Salcedo and I am an aspiring software engineer! I have obtained my B.S in
        Computer Science from the University of Florida. My main focus is developing native iOS apps
        using SwiftUI and creating computer graphic programs using the Metal API
      </p>
    </section>

    <section class="nav-cards">
      <Card
        icon="/icons/user.svg"
        title="About"
        subtitle="Learn more about me"
        color="#4a90e2"
        to="/about"
      />
      <Card
        icon="/icons/folder.svg"
        title="Projects"
        subtitle="Ongoing Projects / Self Learning"
        color="#b80b06"
        to="/projects"
      />
      <Card
        icon="/icons/smartphone.svg"
        title="Apps"
        subtitle="Download some of my apps and let me know what you think!"
        color="#06b811"
      />
      <Card
        icon="/icons/send.svg"
        title="Contact"
        subtitle="Lets get in touch!"
        color="#e3eb02"
        to="/contact"
      />
    </section>

    <section class="featured-apps">
      <h2>Featured Apps</h2>
      <div class="apps-grid">
        <AppCard
          icon="/icons/LiftNotes_logo.png"
          title="Lift Notes"
          subtitle="Log your workouts and make gains!"
          to="https://apps.apple.com/us/app/lift-notes-gym-tracker/id6753324391"
          :external="true"
        />
      </div>
    </section>
  </div>
</template>

<style scoped>
.home {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 1rem;
}

.hero {
  text-align: left;
  padding: 0rem 0;
  margin: 0 auto;
}

.hero-text {
  color: var(--text-primary);
  font-size: 1.4rem;
  line-height: 1.6;
  margin: 0 auto;
}

.nav-cards {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
  gap: 1.5rem;
  padding: 2rem 0;
}

.featured-apps {
  margin-top: rem;
}

.featured-apps h2 {
  font-size: 2rem;
  margin-bottom: 1.5rem;
}

.apps-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr); /* 2 columns */
  gap: 1rem;
}

/* Stack on mobile */
@media (max-width: 768px) {
  .apps-grid {
    grid-template-columns: 1fr;
  }
}
</style>
