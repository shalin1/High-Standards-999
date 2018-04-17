<template>
  <div id="app">
    <HelloWorld msg="High Standards"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue';

export default {
  name: 'app',
  components: {
    HelloWorld
  }
};
</script>

<style lang='scss'>
  @import 'stylesheets/Style'
</style>
