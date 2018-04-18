<template>
  <div id="app">
    <Header/>
    <HeroArea/>
    <ProductCarousel/>
    <Collections />
  </div>
</template>

<script>
import Header from './components/header/Header.vue'
import HeroArea from './components/HeroArea.vue'
import ProductCarousel from './components/ProductCarousel.vue'
import Collections from './components/Collections.vue'

export default {
  name: 'App',
  components: {
    Header,
    HeroArea,
    ProductCarousel,
    Collections
  }
}
</script>

<style lang='scss'>
@import 'stylesheets/Style';
@import 'stylesheets/variables';
</style>
