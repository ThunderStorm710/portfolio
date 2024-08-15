<template>
  <slot></slot>
</template>

<script setup>
import { ref, provide } from 'vue';

const theme = ref('light');

const toggleTheme = () => {
  theme.value = theme.value === 'light' ? 'dark' : 'light';
};

// Fornecendo o tema e a função de alternância para os componentes filhos
provide('theme', theme);
provide('toggleTheme', toggleTheme);
</script>
