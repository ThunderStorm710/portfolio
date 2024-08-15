<template>
  <div :class="theme">
    <Navbar @toggleTheme="toggleTheme" :theme="theme" />
    <router-view :theme="theme" />
    <Footer :theme="theme" />
  </div>
</template>

<script setup>
import { ref } from 'vue';
import Navbar from './components/NavBarComponent.vue';
import Footer from './components/FooterComponent.vue';

// Estado global do tema
// Estado global do tema
const theme = ref('light');

const toggleTheme = () => {
  theme.value = theme.value === 'light' ? 'dark' : 'light';
};
</script>

<style>
/* Estilos globais para fundo */
.light {
  background-color: white;
  color: black;
}

.dark {
  background-color: black;
  color: white;
}

/* Estilos globais para transição */
* {
  transition: background-color 0.5s ease, color 0.5s ease;
}
</style>