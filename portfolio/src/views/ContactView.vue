<template>
  <div class="imagem">
    <section class="contact">
      <div class="content">
        <h2><b>Contactos</b></h2>
      </div>
      <div class="container">
        <div class="contactInfo">
          <div class="box">
            <div class="icon"><i class="fa-solid fa-location-dot"></i></div>
            <div class="text">
              <h3><b>Morada</b></h3>
              <p>Tomar, Santarém, Portugal</p>
            </div>
          </div>
          <div class="box">
            <div class="icon"><i class="fa-solid fa-phone"></i></div>
            <div class="text">
              <h3><b>Telefone</b></h3>
              <p>+351 962865606</p>
            </div>
          </div>
          <div class="box">
            <div class="icon"><i class="fa-solid fa-envelope"></i></div>
            <div class="text">
              <h3><b>Email</b></h3>
              <p>gec.tmr@sapo.pt</p>
            </div>
          </div>
        </div>
        <div class="contactForm">
          <form @submit.prevent="handleSubmit">
            <h2>Envie uma mensagem</h2>
            <div class="inputBox">
              <input type="text" v-model="name" required/>
              <span>Nome</span>
            </div>
            <div class="inputBox">
              <input type="email" v-model="email" required/>
              <span>Email</span>
            </div>
            <div class="inputBox">
              <textarea v-model="message" required></textarea>
              <span>Mensagem</span>
            </div>
            <div class="inputBox">
              <input type="submit" value="Enviar"/>
            </div>
          </form>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const name = ref('');
const email = ref('');
const message = ref('');

const handleSubmit = () => {
  alert('Mensagem enviada com sucesso!');
  // Aqui você pode adicionar a lógica para enviar a mensagem
};
</script>

<style scoped>
/* Estilos adaptados do contacts.html */
</style>
