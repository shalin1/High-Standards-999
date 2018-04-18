<template>
  <div>

    <mq-layout mq='sm'>
      <!-- <a href="#" v-on:click.prevent="showDropDown=!showDropDown"> -->
      <!-- TODO: add slideout modal -->
      <Hamburger />
      <!-- </a> -->
    </mq-layout>

    <mq-layout mq='lg'>
      <ul>
        <li v-for='(url,title) in links' :key='url.id'>
          <a href='url'><h3>{{title}}</h3></a>
        </li>
      </ul>
    </mq-layout>

  </div>
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
div {
  position: relative;
}
a {
  position: relative;
  color: $black;
}
ul{
  display: flex;
  flex-direction: row;
}
li{
  display: block;
  padding-left: 78px;
}
</style>
