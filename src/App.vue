<template>
  <div>
    <Header/>
    <Hero/>
    <About/>
    <Cats/>
    <Gallery/>
    <Footer/>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Hero from './components/Hero.vue'
import About from './components/About.vue'
import Cats from './components/Cats.vue'
import Gallery from './components/Gallery.vue'
import Footer from './components/Footer.vue'

export default {
  components: {
    Header,
    Hero,
    About,
    Cats,
    Gallery,
    Footer
  }
}
</script>

<style>
html, body, #app {
  margin: 0;
  padding: 0;
  height: 100%;
  width: 100%;
  font-family: 'Trebuchet MS', sans-serif;
}
</style>
