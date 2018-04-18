<template>
  <div id="app">
    <Header/>
    <HeroArea/>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import HeroArea from './components/HeroArea.vue'

export default {
  name: 'App',
  components: {
    Header,
    HeroArea
  }
}
</script>

<style lang='scss'>
@import 'stylesheets/Style';
@import 'stylesheets/variables';
</style>
