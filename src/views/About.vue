<template>
  <Header headerTitle="About Me"></Header>
  <BreadcrumbNav />
  <div class="about">
    <!-- Bio section with text and image -->
    <section class="bio-section">
      <div class="bio-text">
        <p>
          Hello once again! I am Edwin Salcedo, a recent graduate from the University of Florida
          looking for full-time opportunities within native iOS development
        </p>
        <p>
          I've always been interested in technology ever since I was young. Whether I was exploring
          websites or playing games I always had the same question, how does it all work? This
          curiosity is what led me to pursue my computer science degree and technology has only
          gotten more fascinating ever since!
        </p>
        <p>
          When I'm not programming I like to play with my cats, go on a nature walk, or explore the
          creative side of myself. Recently I have been picking back up on Blender and Affinity for
          my creative needs
        </p>
        <p>
          While iOS development is my main focus, I believe that the future of technology lies
          within the spatial computing world. I will be exploring this by learning Apple's Metal API
          for graphics programming and will be developing visionOS applications (Once I buy a Vision
          Pro)
        </p>
      </div>

      <div class="bio-image">
        <img src="../assets/92866752.jpeg" alt="Edwin Salcedo" />
      </div>
    </section>

    <section class="skills-section">
      <div class="skill-category">
        <h3>Programming Languages</h3>
      </div>
      <section class="nav-cards">
        <Card
          icon="/icons/swift.png"
          title="Swift"
          subtitle="My favorite language"
          color="#4a90e2"
          to="/about"
        />
        <Card
          icon="/icons/cplusplus.png"
          title="C++"
          subtitle="Used throughout university, graphics programming, and leetcode"
          color="#4a90e2"
          to="/projects"
        />
        <Card
          icon="/icons/csharp.png"
          title="C#"
          subtitle="Wrote my unity scripts with C#"
          color="#4a90e2"
        />
        <Card
          icon="/icons/golang.png"
          title="Go"
          subtitle="Small projects written in Go. Authentication system with middleware"
          color="#4a90e2"
          to="/contact"
        />
      </section>
      <section class="nav-cards">
        <Card
          icon="/icons/sql.png"
          title="SQL"
          subtitle="Basic SQL queries and knowledge. Data migration, indexing, database knowledge"
          color="#4a90e2"
          to="/projects"
        />
        <Card
          icon="/icons/glsl.png"
          title="GLSL"
          subtitle="Written some vertex and fragment shaders for my OpenGL programs"
          color="#4a90e2"
        />
        <Card
          icon="/icons/python.png"
          title="Python"
          subtitle="Experience using A.I models and data mining"
          color="#4a90e2"
          to="/contact"
        />
      </section>

      <div class="skill-category">
        <h3>Frameworks</h3>
      </div>
      <section class="nav-cards">
        <Card
          icon="/icons/swiftui.png"
          title="SwiftUI"
          subtitle="Apple's UI framework. I know SwiftData, CoreData, Combine, and Concurrency aswell"
          color="#4a90e2"
          to="/about"
        />
        <Card
          icon="/icons/unity.png"
          title="Unity Game Engine"
          subtitle="Made a couple of games with Unity. Some of the most fun I've had developing"
          color="#4a90e2"
          to="/projects"
        />
        <Card
          icon="/icons/opengl.png"
          title="OpenGL"
          subtitle="My introduction to graphics programming"
          color="#4a90e2"
        />
        <Card
          icon="/icons/Metal_4.png"
          title="Metal"
          subtitle="Apple's Computer Graphics API"
          color="#4a90e2"
          to="/contact"
        />
        <Card
          icon="/icons/vue.png"
          title="Vue.js"
          subtitle="The only JS framework I like"
          color="#4a90e2"
          to="/contact"
        />
      </section>

      <div class="skill-category">
        <h3>Tools & Technologies</h3>
      </div>
      <section class="nav-cards">
        <Card
          icon="/icons/github.svg"
          title="Github"
          subtitle="Version Control and collaboration"
          color="#4a90e2"
          to="/contact"
        />
        <Card
          icon="/icons/xcode.png"
          title="XCode"
          subtitle="IDE for Swift and Metal development"
          color="#4a90e2"
          to="/contact"
        />
        <Card
          icon="/icons/vscode.png"
          title="VSCode"
          subtitle="My IDE of choice for anything not Apple related"
          color="#4a90e2"
          to="/contact"
        />
        <Card
          icon="/icons/blender.png"
          title="Blender"
          subtitle="3D Modeling program of choice"
          color="#4a90e2"
          to="/contact"
        />
        <Card
          icon="/icons/affinity.png"
          title="Affinity"
          subtitle="RIP Adobe"
          color="#4a90e2"
          to="/contact"
        />
      </section>
    </section>
  </div>
</template>

<script setup>
import Header from '@/components/Header.vue'
import Card from '@/components/Card.vue'
import BreadcrumbNav from '@/components/BreadcrumbNav.vue'
</script>

<style scoped>
.about {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 1rem;
}

.bio-section {
  display: grid;
  grid-template-columns: 1fr auto;
  gap: 3rem;
  align-items: center;
  margin-bottom: 0rem;
  padding-bottom: 0;
}

.bio-text h2 {
  font-size: 2rem;
  margin-bottom: 1.5rem;
}

.bio-text p {
  font-size: 1.4rem;
  line-height: 1.6;
  margin-bottom: 1rem;
}

.bio-image img {
  width: 300px;
  height: auto;
  border-radius: 8px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.4);
}

.skills-section {
  margin-top: 0rem;
}

.skill-category {
  margin-bottom: 1rem;
}

.skill-category h3 {
  font-size: 1.5rem;
  margin-bottom: 1rem;
}

.skill-list {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
}

.skill-item {
  background: #f0f0f0;
  padding: 0.75rem 1.5rem;
  border-radius: 20px;
  font-size: 1rem;
  border: 2px solid #ddd;
}

.nav-cards {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
  gap: 1.5rem;
  padding: 1rem 0;
}

/* Responsive - stack on mobile */
@media (max-width: 768px) {
  .bio-section {
    grid-template-columns: 1fr;
    gap: 2rem;
  }
}
</style>
