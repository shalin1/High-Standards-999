<template>

      <div class='hero-area' :class="$mq">
        <article class='text-side' :class='$mq'>
          <div class='nav-offset' :class="$mq"></div>
          <h1 class='headline' :class='$mq'>High Standards</h1>
          <h3 :class='$mq'>Low Maintance</h3>
          <p :class='$mq'>
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

section {
  background-color: $pistachio;
  height: 587px;
  &.lg {
    height: 680px;
  }
}

.nav-offset {
  height: 60px;
  &.lg {
    height: 84px;
  }
}

.hero-area {
  display: flex;
  flex-direction: column;
  &.lg {
    height: 680px;
    flex-direction: row;
  }
}

.text-side {
  background-color: $pistachio;
  padding: 0 25px;
  color: $black;
  &.lg {
    padding-top: 113px;
    padding-left: 10vw;
  }
}

.headline {
  color: $white;
  padding-bottom: 20px;
  &.lg {
    padding-bottom: 40px;
  }
}

h3 {
  padding-bottom: 6px;
  &.lg {
    padding-bottom: 12px;
  }
}

p {
  &.lg {
    padding-right: 10vw;
  }
}
</style>
