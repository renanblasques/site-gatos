<script setup>
import cats from '../assets/cats.png'
</script>

<template>
  <header class="menu">
    <div class="logo">
      <img :src="cats" alt="Banguela e Soluço" />
      <h1>Banguela & Soluço</h1>
    </div>
    <nav>
      <a href="#sobre">Sobre</a>
      <a href="#gatos">Amor</a>
      <a href="#galeria">Galeria</a>
    </nav>
  </header>
</template>

<style scoped>
.menu {
  width: 100vw;
  background: linear-gradient(to right, #1a1a40, #000);
  padding: 20px 0;
  text-align: center;
  box-shadow: 0 4px 6px rgba(0,0,0,0.5);
  box-sizing: border-box;
}

.logo {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 12px;
}

.logo img {
  width: 40px;
  height: 40px;
  object-fit: contain;
  border-radius: 50%;
  box-shadow: 0 0 4px rgba(0,0,0,0.5);
}

.menu h1 {
  font-size: 2em;
  margin: 0;
  color: #ffcc00;
  text-shadow: 2px 2px #000;
}

nav {
  margin-top: 10px;
}

nav a {
  color: #f0f0f0;
  margin: 0 15px;
  text-decoration: none;
  font-weight: bold;
}

nav a:hover {
  color: #ffcc00;
  text-shadow: 1px 1px #000;
}
</style>
