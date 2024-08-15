<template>
  <v-footer :class="['footer', theme]">
    <div class="footer-content">
      <div class="footer-icons">
        <v-btn
          class="mx-4"
          icon="fas fa-comment"
          variant="plain"
          :color="theme === 'light' ? 'deepskyblue' : 'greenyellow'"
        ></v-btn>
        <v-btn
          class="mx-4"
          icon="fas fa-university"
          variant="plain"
          :color="theme === 'light' ? 'deepskyblue' : 'greenyellow'"
        ></v-btn>
        <v-btn
          class="mx-4"
          icon="fas fa-wifi"
          variant="plain"
          :color="theme === 'light' ? 'deepskyblue' : 'greenyellow'"
        ></v-btn>
        <v-btn
          class="mx-4"
          icon="fas fa-podcast"
          variant="plain"
          :color="theme === 'light' ? 'deepskyblue' : 'greenyellow'"
        ></v-btn>
      </div>

      <div :class="['footer-text', theme === 'light' ? 'text-deepskyblue' : 'text-greenyellow']">
        © {{ new Date().getFullYear() }} — <strong>All Rights Reserved.</strong>
      </div>
    </div>
  </v-footer>
</template>

<script setup>
import { defineProps } from 'vue';

const props = defineProps({
  theme: String,
});
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap');

.footer {
  padding: 20px 50px !important;
  width: 100%;
  transition: background-color 0.5s ease, color 0.5s ease;
  font-family: 'Poppins', sans-serif;
  display: flex;
  justify-content: center;
  align-items: center;
}

/* Light Theme */
.footer.light {
  background-color: white; /* Fundo branco para o tema claro */
  color: deepskyblue;
}

.footer.light .text-deepskyblue {
  color: deepskyblue !important;
}

.footer.light .v-btn {
  color: deepskyblue;
}

/* Dark Theme */
.footer.dark {
  background-color: black; /* Fundo preto para o tema escuro */
  color: greenyellow;
}

.footer.dark .text-greenyellow {
  color: greenyellow !important;
}

.footer.dark .v-btn {
  color: greenyellow;
}

/* Footer Content Layout */
.footer-content {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
}

.footer-icons {
  display: flex;
  gap: 20px;
}

.footer-text {
  font-size: 0.9rem;
  font-weight: bold;
}

/* Adjust layout for mobile view */
@media (max-width: 768px) {
  .footer {
    flex-direction: column;
    align-items: center;
    text-align: center;
  }

  .footer-content {
    flex-direction: column;
    gap: 15px;
  }

  .footer-icons {
    justify-content: center;
  }
}
</style>
