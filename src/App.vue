<template>
  <div id="app">
    <Header/>
    <HeroArea/>
    <ProductCarousel/>
  </div>
</template>

<script>
import Header from './components/header/Header.vue'
import HeroArea from './components/HeroArea.vue'
import ProductCarousel from './components/ProductCarousel.vue'

export default {
  name: 'App',
  components: {
    Header,
    HeroArea,
    ProductCarousel
  }
}
</script>

<style lang='scss'>
@import 'stylesheets/Style';
@import 'stylesheets/variables';
</style>
