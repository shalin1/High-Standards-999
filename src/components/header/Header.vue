<template>
  <nav class='header-container'>
    <NavLinks/>
    <Logo />
    <Cart />
  </nav>
</template>

<script>
import NavLinks from './NavLinks.vue'
import Cart from './Cart.vue'
import Logo from './Logo.vue'

export default {
  name: 'Header',
  props: {
    label: String
  },
  components: {
    NavLinks,
    Cart,
    Logo
  }
}
</script>

<style lang='scss' scoped>
@import '../../stylesheets/variables';
.header-container {
  background-color: rgba(32, 47, 47, 0.1);
  color: $black;
  border-style: none;
  position: absolute;
  width: 100vw;
  top:0;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 20px;
  height: 60px;
}

</style>
