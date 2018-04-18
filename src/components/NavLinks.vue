<template>
  <nav>
    <button>
      <Icon type='hamburger' />
    </button>
    <ul>
      <NavLink label='Men'></NavLink>
      <NavLink label='Women'></NavLink>
      <NavLink label='Magazine`'></NavLink>
      <NavLink label='Stores'></NavLink>
    </ul>
  </nav>
</template>

<script>
import NavLink from './NavLink.vue'

export default {
  name: 'NavLinks',
  components: {
    NavLink
  }
}
</script>

<style lang='scss' scoped>

</style>
