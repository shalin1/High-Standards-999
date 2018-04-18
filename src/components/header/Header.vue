<template>
  <div class='header-container'>

    <mq-layout mq="sm">
      <nav class='sm'>
        <NavLinks/>
        <Logo />
        <Cart />
      </nav>
    </mq-layout>

    <mq-layout mq="lg">
      <nav class='lg'>
        <div>
          <Logo />
          <NavLinks/>
        </div>
        <Cart />
      </nav>
    </mq-layout>

  </div>
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
  background-color: $transparent-gray;
  color: $black;
  border-style: none;
  position: absolute;
  width: 100vw;
  top: 0;
}
nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 20px;
  height: 60px;
  &.lg {
    height: 84px;
    padding: 24px;
  }
  & div {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
  }
}
</style>
