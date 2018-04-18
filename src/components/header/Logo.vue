<template>
  <a href='/'><img src='../../assets/logo.png' /></a>
</template>

<script>
export default {
  name: 'HeaderButton',
}
</script>

<style lang='scss' scoped>
@import '../../stylesheets/variables';
  img {
    color: $black;
    filter: invert(100%);
    height: 36px;
    width: 36px;
  }
</style>
