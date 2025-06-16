<script setup>
import { ref, onMounted } from 'vue'
import banguela from '../assets/Banguela.jpeg'
import soluco from '../assets/Soluço.jpeg'
import dragon1 from '../assets/banguelaCat.png'
import dragon2 from '../assets/soluçodragon.png'

const aboutRef = ref(null)
const showDragons = ref(false)

onMounted(() => {
  const observer = new IntersectionObserver(
    ([entry], obs) => {
      const hasScrolled = window.scrollY > 50
      if (entry.isIntersecting && hasScrolled) {
        showDragons.value = true
      }
    },
    {
      threshold: 0.5,
    }
  )

  if (aboutRef.value) {
    observer.observe(aboutRef.value)
  }
})

</script>

<template>
  <section class="sobre" id="sobre" ref="aboutRef">
    <div class="dragons">
      <img
        :src="dragon1"
        alt="Banguela voando"
        class="dragon dragon-1"
        :class="{ active: showDragons }"
      />
      <img
        :src="dragon2"
        alt="Soluço voando"
        class="dragon dragon-2"
        :class="{ active: showDragons }"
      />
    </div>

    <div class="content">
      <div class="text">
        <h2>Sobre os Dragões</h2>
        <p>
          Banguela e Soluço não são apenas gatos, são companheiros inseparáveis, 
          cheios de personalidade e afeto. Banguela, cheio de energia, vive explorando 
          cada canto da casa com olhos atentos e passos ágeis. Mas por trás de sua independência, 
          esconde-se um lado carinhoso que adora um amassar de pãozinho no fim do dia.
        </p>
        <p>
          Já seu irmão Soluço, é o mais tranquilo dos dois. Com seu jeito calmo e 
          carente, está sempre em busca de colo e atenção, ronronando satisfeito ao menor 
          sinal de carinho. Juntos, eles fazem da rotina algo especial, trazendo momentos caóticos
          e momentos alegres dentro de casa.
        </p>
      </div>
      <div class="images">
        <img :src="banguela" alt="Banguela" />
        <img :src="soluco" alt="Soluço" />
      </div>
    </div>
  </section>
</template>

<style scoped>
.sobre {
  position: relative;
  background: linear-gradient(to bottom, #2a2a2a, #1a1a1a);
  color: #f4f4f4;
  padding: 80px 20px;
  overflow: hidden;
}

.content {
  max-width: 1200px;
  margin: 0 auto;
  display: flex;
  flex-wrap: wrap;
  gap: 40px;
  align-items: center;
  justify-content: center;
}

.text {
  flex: 1 1 400px;
}

.text h2 {
  font-size: 2.8rem;
  margin-bottom: 20px;
  color: #ffcc00;
}

.text p {
  font-size: 1.1rem;
  line-height: 1.7;
  margin-bottom: 15px;
}

.images {
  display: flex;
  flex: 1 1 300px;
  flex-direction: column;
  gap: 20px;
  align-items: center;
}

.images img {
  width: 200px;
  border-radius: 20px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.6);
  transition: transform 0.3s ease;
}

.images img:hover {
  transform: scale(1.05) rotate(-2deg);
}

.dragons {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  pointer-events: none;
  z-index: 0;
}

.dragon {
  position: absolute;
  width: 400px;
  opacity: 0;
  transition: opacity 0.5s ease;
}

.dragon-1 {
  top: -100px;
  left: -120px;
}

.dragon-2 {
  top: -80px;
  right: -120px;
}

.dragon-1.active {
  animation: flyAcross 8s ease-in-out forwards;
}

.dragon-2.active {
  animation: flyAcrossReverse 9s ease-in-out forwards;
}

@keyframes flyAcross {
  0% {
    transform: translateX(0) translateY(0) scale(0.5) rotate(-15deg);
    opacity: 0;
  }
  20% {
    opacity: 1;
  }
  100% {
    transform: translateX(120vw) translateY(100vh) scale(1.2) rotate(20deg);
    opacity: 0;
  }
}

@keyframes flyAcrossReverse {
  0% {
    transform: translateX(0) translateY(0) scale(0.5) rotate(15deg);
    opacity: 0;
  }
  20% {
    opacity: 1;
  }
  100% {
    transform: translateX(-120vw) translateY(100vh) scale(1.2) rotate(-20deg);
    opacity: 0;
  }
}
</style>
