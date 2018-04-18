<template>
  <nav class='header-container'>
    <NavLinks/>
    <Logo />
    <Icon type='cart' />
  </nav>
</template>

<script>
import NavLinks from './NavLinks.vue'
import Icon from './Icon.vue'
import Logo from './Logo.vue'

export default {
  name: 'Header',
  props: {
    label: String
  },
  components: {
    NavLinks,
    Icon,
    Logo
  }
}
</script>

<style lang='scss' scoped>
@import '../stylesheets/variables';
nav {
  background-color: rgba(32, 47, 47, 0.1);
  color: $black;
  border-style: none;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 20px;
}

</style>
