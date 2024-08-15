<template>
  <div :class="['home', theme]">
    <Navbar :theme="theme" />
    <header :class="['hero', theme]">
      <div class="hero-content">
        <h1>Hello,</h1>
        <h2>I'm Pedro Ascensão</h2>
        <p>Web Designer & Developer</p>
        <router-link to="/contact" class="btn">Contact Me</router-link>
      </div>
      <img :src="personImage" alt="Person" class="hero-image" />
    </header>
    <div :class="['arrow-down', theme]">
      <a href="#about-me" @click.prevent="scrollToSection"><i class="fas fa-chevron-down"></i></a>
    </div>
    <!-- About Section -->
    <section :class="['about', theme]" id="about-me">
      <div class="about-content">
        <h2>About Me</h2>
        <p>I am a Computer Engineering student and am currently studying a Master's degree at the University of Coimbra (UC).</p>
        <p>I have a strong interest in a wide variety of programming languages and technologies, with a focus on software
          applications and web and backend development.</p> 
        <p>I am eager for knowledge and that is why I always strive to
          continually encourage my learning and my ability to solve problems allows me to quickly adapt to new technologies
          and face more complex challenges.</p>
        <!-- Logos Section -->
        <div class="logos">
          <img :src="cisuc" alt="CISUC Logo" class="logo" />
          <img :src="uc" alt="UC Logo" class="logo" />
        </div>
      </div>
    </section>
    <!-- Conhece-me Section -->
    <section :class="['discover', theme]">
      <router-link to="/about" class="discover-btn">Get know me</router-link>
    </section>
  </div>
</template>

<script setup>
import { defineProps } from 'vue';

// Importando as imagens
import cisuc from '@/assets/CISUC.png';
import uc from '@/assets/UC.png';

const props = defineProps({
  theme: String,
});

function scrollToSection() {
  const section = document.getElementById('about-me');
  section.scrollIntoView({ behavior: 'smooth' });
}
</script>

<style scoped>
/* Hero Section */
.hero {
  position: relative;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 100px 50px;
  min-height: 100vh;
  transition: background-color 0.5s ease, color 0.5s ease;
}

.hero.light {
  background-color: white;
  color: black;
}

.hero.dark {
  background-color: #000;
  color: #fff;
}

.hero-content {
  max-width: 50%;
}

.hero-content h1 {
  font-size: 3rem;
  margin: 0;
}

.hero-content h2 {
  font-size: 2.5rem;
  margin: 10px 0;
  color: #f0c040;
}

.hero-content p {
  font-size: 1.2rem;
  margin-bottom: 20px;
}

.hero-content .btn {
  padding: 10px 20px;
  background-color: transparent;
  border: 2px solid #f0c040;
  color: #f0c040;
  text-decoration: none;
  font-size: 1rem;
  transition: background-color 0.3s ease;
}

.hero-content .btn:hover {
  background-color: #f0c040;
  color: #000;
}

.hero-image {
  max-width: 40%;
}

/* Arrow Down */
.arrow-down {
  position: absolute;
  bottom: 20px;
  left: 50%;
  transform: translateX(-50%);
  font-size: 2rem;
  transition: color 0.5s ease;
}

.arrow-down.light {
  color: black;
}

.arrow-down.dark {
  color: #fff;
}

/* About Section */
.about {
  padding: 50px;
  text-align: center;
  transition: background-color 0.5s ease, color 0.5s ease;
}

.about.light {
  background-color: #f4f4f4;
  color: #333;
}

.about.dark {
  background-color: #333;
  color: #f4f4f4;
}

.about-content {
  max-width: 800px;
  margin: 0 auto;
}

.about-content h2 {
  font-size: 2rem;
  margin-bottom: 20px;
}

.about-content p {
  font-size: 1.2rem;
  line-height: 1.8rem;
  margin-bottom: 20px;
}

/* Logos Section */
.logos {
  display: flex;
  justify-content: center;
  gap: 30px;
  margin-top: 40px;
}

.logo {
  height: 100px; /* Define a altura fixa */
  width: auto; /* Mantém a proporção correta */
  object-fit: contain; /* Garante que a imagem seja ajustada corretamente */
}
/* Discover Section */
.discover {
  padding: 30px;
  text-align: center;
  transition: background-color 0.5s ease, color 0.5s ease;
}

.discover.light {
  background-color: #f4f4f4;
  color: #333;
}

.discover.dark {
  background-color: #333;
  color: #f4f4f4;
}

.discover-btn {
  padding: 15px 30px;
  background-color: #f0c040;
  color: #000;
  text-decoration: none;
  font-size: 1.2rem;
  font-weight: bold;
  border-radius: 5px;
  transition: background-color 0.3s ease;
}

.discover-btn:hover {
  background-color: #000;
  color: #f0c040;
}
</style>
