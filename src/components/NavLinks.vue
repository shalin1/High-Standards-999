<template>
  <nav>
    <a href="#" v-on:click.prevent="showDropDown=!showDropDown"/>
      <Hamburger/>
    </a>
    <div>
      <ul>
        <NavLink v-for="link in links" class="list">{{name}}</NavLink>
      </ul>
    </div>
    <!-- todo: implement nav links on dropdown -->
    <!-- -->
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
  data: {
    showDropDown: true,
    links: [
      {name: "Men"},
      {name: "Women"},
      {name: "Magazine"},
      {name: "Stores"},
    ]
  },
}


</script>

<style lang='scss' scoped>

</style>
