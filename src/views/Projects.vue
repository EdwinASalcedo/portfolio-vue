<script setup>
import BreadcrumbNav from '@/components/BreadcrumbNav.vue'
import Card from '@/components/Card.vue'
import Header from '@/components/Header.vue'
</script>

<template>
  <Header headerTitle="Personal Projects"></Header>
  <BreadcrumbNav />
  <div class="home">
    <section class="hero">
      <p class="hero-text">Checkout the repos of my personal projects below</p>
    </section>

    <section class="nav-cards">
      <Card
        icon="/icons/LiftNotes_logo.png"
        title="Lift Log"
        subtitle="iOS App to track your workouts and make gains"
        color="#b80b06"
        to="https://github.com/EdwinASalcedo/LiftLogSwiftData"
        :external="true"
      />
      <Card
        icon="/icons/cg.png"
        title="OpenGL"
        subtitle="Learned how to load models, implement lighting and toggle textures"
        color="#b80b06"
        to="https://github.com/EdwinASalcedo/OpenGLTextureToggler"
        :external="true"
      />
      <Card
        icon="/icons/toydash.png"
        title="Toy Dash"
        subtitle="Help the toy robot back to where it belongs. 3D game made with Unity"
        color="#b80b06"
        to="https://github.com/Viscerus/3878_GroupProject"
        :external="true"
      />
      <Card
        icon="📱"
        title="NeruoStock"
        subtitle="Stock prediction A.I model using YahooFinance"
        color="#b80b06"
        to="https://github.com/EdwinASalcedo/NeuroStock-Forecast"
        :external="true"
      />
      <Card
        icon="✉️"
        title="MunchIn"
        subtitle="Find food near you and notify freinds on what you are craving"
        color="#b80b06"
        to="https://github.com/EdwinASalcedo/MunchIn"
        :external="true"
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
