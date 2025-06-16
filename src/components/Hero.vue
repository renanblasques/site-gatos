<script setup>
import background from '../assets/background.png'
</script>

<template>
  <section class="hero">
     <div
  class="overlay"
  :style="{
    backgroundImage: `url(${background})`,
    backgroundRepeat: 'no-repeat',
    backgroundSize: 'cover',
    backgroundPosition: 'center'
  }"
>
    <div class="content">
      <h2>Banguela & Soluço</h2>
      <p>Dois pequenos dragões prontos para conquistar seu coração</p>
      <a href="#sobre" class="btn">Conheça a história</a>
    </div>
  </div>
  </section>
</template>

<style scoped>
.hero {
  height: 100vh;
  width: 100vw;
  background-image: url('https://images.unsplash.com/photo-1606312616494-895f22f59466?fit=crop&w=1400&q=80');
  background-size: cover;
  background-position: center;
  position: relative;
  overflow: hidden;
}

.overlay {
  background-color: rgba(56, 56, 56, 0.6);
  height: 100%;
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  position: relative;
}

.content {
  text-align: center;
  color: #f8f8f8;
  max-width: 700px;
  padding: 0 20px;
  z-index: 2;
}

.content h2 {
  font-size: 3rem;
  margin-bottom: 10px;
  color: #ffcc00;
  text-shadow: 2px 2px #000;
}

.content p {
  font-size: 1.2rem;
  margin-bottom: 20px;
  font-style: italic;
}

.btn {
  background-color: #ffcc00;
  color: #1a1a1a;
  padding: 12px 24px;
  text-decoration: none;
  font-weight: bold;
  border-radius: 8px;
  box-shadow: 2px 2px 8px #000;
  transition: background-color 0.3s ease;
}

.btn:hover {
  background-color: #e6b800;
}
</style>
