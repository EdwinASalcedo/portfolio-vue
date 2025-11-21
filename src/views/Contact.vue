<script setup>
import BreadcrumbNav from '@/components/BreadcrumbNav.vue'
import Card from '@/components/Card.vue'
import Header from '@/components/Header.vue'
import { Send } from 'lucide-vue-next'
</script>

<template>
  <Header headerTitle="Connect & Contact"></Header>
  <BreadcrumbNav />
  <div class="home">
    <section class="hero">
      <p class="hero-text">
        Connect with me on whatever platform of your choosing. Do some stalking, connect with me, DM
        me, etc...
      </p>
    </section>

    <section class="nav-cards">
      <Card
        icon="/icons/linkedin.svg"
        title="LinkedIn"
        subtitle="Connect with me"
        color="#e3eb02"
        to="https://linkedin.com/in/edwin-a-salcedo/"
        :external="true"
      />
      <Card
        icon="/icons/x.svg"
        title="Twitter / X"
        subtitle="Some updates on my iOS Development. Dm me"
        color="#e3eb02"
        to="https://twitter.com/EdSauce_edo"
        :external="true"
      />
      <Card
        icon="/icons/mail.svg"
        title="Email"
        subtitle="Email me for any opportunities or questions edwin.a.salcedo02@gmail.com"
        color="#e3eb02"
      />
      <Card
        icon="/icons/instagram.svg"
        title="Instagram"
        subtitle="Follow me. I try and make content about my iOS development journey and other general life updates/rants"
        color="#e3eb02"
      />
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
  font-size: 1.4rem;
  line-height: 1.6;
  margin: 0 auto;
  color: var(--text-primary);
}

.nav-cards {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
  gap: 1.5rem;
  padding: 2rem 0;
}
</style>
