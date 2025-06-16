<template>
  <section class="galeria" id="galeria">
    <h2 class="titulo-galeria">Momentos Mágicos</h2>
    <div class="galeria-flex">
      <div
        class="galeria-item"
        v-for="(img, index) in imagens"
        :key="index"
      >
        <img :src="img" :alt="'Foto ' + (index + 1)" />
      </div>
    </div>
  </section>
</template>

<script setup>
import img1 from '@/assets/gatos1.jpeg'
import img2 from '@/assets/gatos2.jpeg'
import img3 from '@/assets/gatos3.jpeg'
import img4 from '@/assets/gatos4.jpeg'
import img5 from '@/assets/gatos5.jpeg'
import img6 from '@/assets/gatos6.jpeg'

const imagens = [img1, img2, img3, img4, img5, img6]
</script>

<style scoped>
.galeria {
  background: linear-gradient(to bottom, #2a2a2a, #1a1a1a);
  padding: 100px 20px;
  color: #fff;
  text-align: center;
}

.titulo-galeria {
  font-size: 2.5rem;
  color: #ffcc00;
  margin-bottom: 60px;
  text-shadow: 0 0 10px #000;
}

.galeria-flex {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 50px;
  max-width: 740px;
  margin: 0 auto;
}

.galeria-item {
  width: 180px;
  border-radius: 16px;
  overflow: hidden;
  height: 220px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.6);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.galeria-item:hover {
  transform: scale(1.05);
  box-shadow: 0 6px 20px rgba(255, 204, 0, 0.3);
}

.galeria-item img {
  width: 100%;
  height: auto;
  display: block;
}
</style>
