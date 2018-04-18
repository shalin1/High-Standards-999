<template>
  <nav>
    <a href="#" v-on:click.prevent="showDropDown=!showDropDown">
      <Hamburger></Hamburger>
    </a>
    <!-- <div>
      <ul>
        <NavLink v-for="link in links" class="list" v-bind:key="link.id">{{link.name}}</NavLink>
      </ul>
    </div> -->
  </nav>
</template>

<script>
import NavLink from './NavLink.vue'
import Hamburger from './Hamburger.vue'

export default {
  name: 'NavLinks',
  components: {
    NavLink,
    Hamburger
  },
  data: function () {
    return {
      showDropDown: false,
      links: [
        { name: 'Men' },
        { name: 'Women' },
        { name: 'Magazine' },
        { name: 'Stores' }
      ]
    }
  }
}
</script>

<style lang='scss' scoped>
</style>
