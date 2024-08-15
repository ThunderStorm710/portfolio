<template>
  <nav :class="['navbar', theme]">
    <div class="logo">Pedro Ascensão</div>
    <ul class="nav-links">
      <li>
        <router-link to="/">Home</router-link>
      </li>
      <li>
        <router-link to="/about">About</router-link>
      </li>
      <li>
        <router-link to="/portfolio">Portfolio</router-link>
      </li>
      <li>
        <router-link to="/services">Services</router-link>
      </li>
      <li>
        <router-link to="/blog">Blog</router-link>
      </li>
      <li>
        <router-link to="/contact">Contact</router-link>
      </li>
    </ul>
    <button class="theme-toggle" @click="$emit('toggleTheme')">
      <i :class="[theme === 'light' ? 'fas fa-sun' : 'fas fa-moon']"></i>
    </button>
  </nav>
</template>

<script setup>
import { defineProps } from 'vue';

const props = defineProps({
  theme: String,
});
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap');

body {
  font-family: 'Poppins', sans-serif;
}

.logo {
  font-size: 1rem;
  font-weight: bold;
}

/* General Navbar Styles */
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 20px 50px;
  width: 100%;
  top: 0;
  position: absolute;
  z-index: 100;
  transition: background-color 0.5s ease, color 0.5s ease;
  font-family: 'Poppins', sans-serif;
}

.nav-links {
  list-style: none;
  display: flex;
  gap: 30px;
}

/* Adjust layout for mobile view */
.mobile-menu-toggle {
  display: none;
}

@media (max-width: 768px) {
  .navbar {
    padding: 15px 20px;
  }

  .nav-links {
    position: absolute;
    top: 70px;
    left: 0;
    width: 100%;
    flex-direction: column;
    background-color: inherit;
    text-align: center;
    transition: all 0.3s ease-in-out;
    transform: translateY(-100%);
    opacity: 0;
    pointer-events: none;
  }

  .nav-links.mobile-nav {
    transform: translateY(0);
    opacity: 1;
    pointer-events: all;
  }

  .nav-links li {
    margin: 10px 0;
  }

  .mobile-menu-toggle {
    display: block;
    background: none;
    border: none;
    cursor: pointer;
    font-size: 1.5rem;
    padding: 10px;
    transition: color 0.5s ease;
  }

  .theme-toggle {
    margin-left: auto;
  }
}

/* Light Theme */
.navbar.light {
  background-color: white;
  color: deepskyblue;
}

.navbar.light .nav-links a {
  color: deepskyblue;
}

.navbar.light .nav-links a:hover::before {
  border-color: deepskyblue;
}

.navbar.light .theme-toggle i {
  color: deepskyblue;
}

/* Dark Theme */
.navbar.dark {
  background-color: black;
  color: greenyellow;
}

.navbar.dark .nav-links a {
  color: greenyellow;
}

.navbar.dark .nav-links a:hover::before {
  border-color: greenyellow;
}

.navbar.dark .theme-toggle i {
  color: greenyellow;
}

/* Navbar Links */
.nav-links a {
  text-decoration: none;
  font-size: 1rem;
  font-weight: bold;
  padding: 10px 15px;
  position: relative;
  transition: color 0.5s ease, border-color 0.5s ease;
}

.nav-links a::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  border: 2px solid transparent;
  opacity: 0;
  transition: opacity 0.5s ease, border-color 0.5s ease;
  border-radius: 5px;
  pointer-events: none;
}

.nav-links a:hover::before {
  opacity: 1;
}

/* Theme Toggle Button */
.theme-toggle {
  background: none;
  border: none;
  cursor: pointer;
  font-size: 1.5rem;
  padding: 10px;
  transition: color 0.5s ease;
}
</style>
