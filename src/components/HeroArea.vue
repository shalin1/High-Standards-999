<template>
    <div class='hero-area'>
      <div class='nav-offset'></div>
      <article class='text-side'>
        <h1>High Standards</h1>
        <h3>Low Maintance</h3>
        <p>
          Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
        </p>
      </article>
      <Carousel/>
    </div>
</template>

<script>
import Carousel from './Carousel.vue'
export default {
  name: 'HeroArea',
  components: {
    Carousel
  }
}
</script>

<style lang='scss' scoped>
@import '../stylesheets/variables';
.nav-offset {
  height: 80px;
  background-color: $pistachio;
}
.text-side {
  background-color: $pistachio;

  padding: 25px;
  color: $black;
}
h1 {
  color: $white;
  padding-bottom: 20px;
}
h3 {
  padding-bottom: 10px;
}
</style>
