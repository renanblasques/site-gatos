<template>
  <section id="gatos" class="favoritos-section">
    <h2 class="titulo">Coisas que Banguela e Soluço amam</h2>
    <div class="items-flex">
      <div class="fav-circle" v-for="item in favoritos" :key="item.nome">
        <img :src="item.img" :alt="item.nome" />
        <span>{{ item.nome }}</span>
      </div>
    </div>
  </section>
</template>

<script setup>
const favoritos = [
  {
    nome: "Caixa de Papelão",
    img: new URL('@/assets/caixa.png', import.meta.url).href
  },
  {
    nome: "Bolinhas",
    img: new URL('@/assets/bolinha.png', import.meta.url).href
  },
  {
    nome: "Filtro de água",
    img: new URL('@/assets/filtro.png', import.meta.url).href
  },
  {
    nome: "Sachê Whiskas",
    img: new URL('@/assets/whiskas.png', import.meta.url).href
  },
  {
    nome: "Janela com Sol",
    img: new URL('@/assets/janela.png', import.meta.url).href
  },
  {
    nome: "Cobertor Quentinho",
    img: new URL('@/assets/cobertor.png', import.meta.url).href
  },
]
</script>

<style scoped>
.favoritos-section {
  background: linear-gradient(to bottom, #0f0c29, #302b63, #24243e);
  color: #fff;
  padding: 100px 20px;
  text-align: center;
  min-height: 100vh;
}

.titulo {
  font-size: 2.5em;
  margin-bottom: 60px;
  color: #ffe066;
  text-shadow: 0 0 10px #000;
}

.items-flex {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 60px;
  max-width: 800px;
  margin: 0 auto;
  padding: 0 10px;
}

.fav-circle {
  flex: 1 1 200px; 
  max-width: 180px;
  height: 180px;
  background: rgba(255, 255, 255, 0.05);
  border: 3px solid #ffe066;
  border-radius: 50%;
  box-shadow: 0 0 20px rgba(255, 204, 0, 0.3);
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  transition: transform 0.3s ease;
  animation: flutuar 4s ease-in-out infinite;
  padding: 20px;
  backdrop-filter: blur(4px);
}

.fav-circle:hover {
  transform: scale(1.1) rotate(2deg);
  box-shadow: 0 0 30px rgba(255, 204, 0, 0.5);
}

.fav-circle img {
  width: 90px;
  height: 90px;
  object-fit: contain;
  margin-bottom: 10px;
}

.fav-circle span {
  font-size: 0.9em;
  color: #fff;
}

@keyframes flutuar {
  0%, 100% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-8px);
  }
}

</style>