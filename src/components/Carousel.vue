<template>
  <div>
    <img src='../assets/carousel-hero.jpg' />
    <button>Start Shopping</button>
  </div>
</template>

<script>
export default {
  name: 'Carousel',
}
</script>

<style lang='scss' scoped>
@import '../stylesheets/variables';
div {
  position: relative
}
img{
width:100%;
}
button{
  background: $black;
  color: $white;
  position: absolute;
  bottom:0;
  right:0;
  border-style: none;
  height: 60px;
  width: 50vw;
}
</style>
