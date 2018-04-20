<template>
  <div class='header-container'>

    <mq-layout mq="sm">
      <nav class='sm'>
        <a href="#" v-on:click.prevent="showDropDown=!showDropDown">
          <Hamburger v-if="!showDropDown" />
          <span v-else>X</span>
          <transition name='slide-fade'>
            <div v-if='showDropDown' class='mobile-links'>
            <a class='mobile-link'  v-for='(url,title) in links' :key='url.id' href='url'><h3>{{title}}</h3></a>
          </div>
          </transition>
        </a>
        <a v-if='!showDropDown' href='/'><img class='logo' src='../../assets/logo.png' /></a>
        <Cart />
      </nav>
    </mq-layout>

    <mq-layout mq="lg">
      <nav class='lg'>
        <div>
          <a href='/'><img class='logo' src='../../assets/logo.png' /></a>
          <ul>
            <li v-for='(url,title) in links' :key='url.id'>
              <a href='url'><h3>{{title}}</h3></a>
            </li>
          </ul>
        </div>
        <Cart />
      </nav>
    </mq-layout>

  </div>
</template>

<script>
import NavLinks from './NavLinks.vue'
import Cart from './Cart.vue'
import Hamburger from './Hamburger.vue'

export default {
  name: 'Header',
  props: {
    label: String
  },
  components: {
    NavLinks,
    Cart,
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
.header-container {
  background-color: $transparent-gray;
  color: $black;
  z-index: 10;
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
.logo {
  color: $black;
  filter: invert(100%);
  height: 36px;
  width: 36px;
}
li {
  display: block;
  padding-left: 78px;
}
ul {
  display: flex;
  flex-direction: row;
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
