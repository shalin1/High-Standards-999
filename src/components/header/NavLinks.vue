<template>
  <nav>
      <!-- <a href="#" v-on:click.prevent="showDropDown=!showDropDown"> -->
        <Hamburger></Hamburger>
      <!-- </a> -->
      <ul v-if='showDropDown'>
        <li v-for='(url,title) in links' :key='url.id'>
          <a href='url'><h3>{{title}}</h3></a>
        </li>
      </ul>

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
  data () {
    return {
      showDropDown: false,
      links: {
        'Men': '#',
        'Women': '#',
        'Magazine': '#',
        'Store': '#'
      }
    }
  }
}
</script>

<style lang='scss' scoped>
@import '../../stylesheets/variables';
nav {
  position: relative;
}
a {
  position: relative;
}
ul{
  position: absolute;
left: -1px;
overflow: hidden;
background: $transparent-gray;
}
li{
  display: block;
}
</style>
