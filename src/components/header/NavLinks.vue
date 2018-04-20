<template>
  <div class='nav-link-container'>

    <mq-layout mq='sm'>
      <a href="#" v-on:click.prevent="showDropDown=!showDropDown">
        <Hamburger />
        <transition name='slide-fade'>
          <div v-if='showDropDown' class='mobile-links'>
          <a class='mobile-link'  v-for='(url,title) in links' :key='url.id' href='url'><h3>{{title}}</h3></a>
        </div>
        </transition>
      </a>
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
import Hamburger from './Hamburger.vue'

export default {
  name: 'NavLinks',
  components: {
    Hamburger
  },
  data() {
    return {
      showDropDown: false,
      links: {
        Men: '#',
        Women: '#',
        Magazine: '#',
        Store: '#'
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
ul {
  display: flex;
  flex-direction: row;
}
li {
  display: block;
  padding-left: 78px;
}
.nav-link-container {
  position: relative;
}
.mobile-links {
  position: absolute;

  display: flex;
  flex-direction: row;
  // background: $white;
}
.mobile-link{
  padding-right: 10vw;
}
.slide-fade-enter-active {
  transition: all .6s ease;
}
.slide-fade-leave-active {
  transition: all .8s cubic-bezier(1.0, 0.5, 0.8, 1.0);
}
.slide-fade-enter, .slide-fade-leave-to {
  transform: translateX(-80px);
  opacity: 0;
}
</style>
