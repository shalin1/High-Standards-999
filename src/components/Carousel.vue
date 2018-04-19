<template>
  <div>
    <img :class='$mq' src='../assets/carousel-hero.jpg' />
    <button :class='$mq'>Start Shopping</button>
  </div>
</template>

<script>
export default {
  name: 'Carousel'
}
</script>

<style lang='scss' scoped>
@import '../stylesheets/variables';

div {
  position: relative;
  z-index: 1;
}

img {
  object-fit: cover;
  width: 100vw;
  &.lg {
    width: 57.3vw;
    height: 680px;
  }
}

button {
  background: $black;
  color: $white;
  position: absolute;
  bottom: 0;
  right: 0;
  border-style: none;
  height: 60px;
  width: 50vw;
  &.lg{
    width: 25vw;
  }
}
</style>
