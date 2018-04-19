<template>
  <div id="app">
    <Header/>
    <HeroArea/>
    <ProductCarousel/>
    <Collections />
    <Footer />
  </div>
</template>

<script>
import Header from './components/header/Header.vue'
import HeroArea from './components/HeroArea.vue'
import ProductCarousel from './components/ProductCarousel.vue'
import Collections from './components/Collections.vue'
import Footer from './components/Footer.vue'
import Vue from 'vue'
import VueMq from 'vue-mq'
import VueAwesomeSwiper from 'vue-awesome-swiper'

Vue.use(VueMq, {
  breakpoints: {
    sm: 768,
    lg: Infinity
  }
})
Vue.use(VueAwesomeSwiper,
 /* { default global options } */
)

export default {
  name: 'App',
  components: {
    Header,
    HeroArea,
    ProductCarousel,
    Collections,
    Footer
  }
}
</script>

<style lang='scss'>
@import 'stylesheets/Style';
@import 'stylesheets/variables';
</style>
