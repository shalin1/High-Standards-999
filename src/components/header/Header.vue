<template>
  <div>

    <mq-layout mq="sm">
      <nav class='header-container' :class='{ inverted : showMobileLinks}'>
        <a href="#" v-on:click.prevent="showMobileLinks=!showMobileLinks">
          <transition name='fade' mode='out-in'>
            <h2 class='x' v-if="showMobileLinks">✕</h2>
            <Hamburger v-else/>
          </transition>
        </a>

        <transition name='logo-link-slide' mode='out-in'>
          <div v-if='showMobileLinks' class='mobile-links'>
            <a  v-for='(url,title) in links' :key='url.id' href='url'><h3 class='mobile-link'>{{title}}</h3></a>
          </div>
          <a v-else href='/'><img class='logo' src='../../assets/logo.png' /></a>
        </transition>
        <Cart />


      </nav>
    </mq-layout>

    <mq-layout mq="lg">
      <nav class='header-container lg'>
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
      showMobileLinks: false,
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
  transition: 0.8s;
  background-color: $transparent-gray;
  color: $black;
  z-index: 10;
  position: absolute;
  width: 100vw;
  top: 0;
  &.inverted{
    transition: 0.8s;
    background-color: $black;
    fill: $white;
  }
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
.x{
  color:$white;
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
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
}
.mobile-link{
  padding: 0 4vw;
  color: $white;
}
.fade-enter-active {
  transition: all .3s cubic-bezier(1.0, 0.5, 0.8, 1.0);
}
.fade-leave-active {
  transition: all .3s cubic-bezier(1.0, 0.5, 0.8, 1.0);
}
.fade-enter, .fade-leave-to {
  opacity: 0;
}
.logo-link-slide-enter-active {
  transition: all .2s cubic-bezier(1.0, 0.5, 0.8, 1.0);
}
.logo-link-slide-leave-active {
  transition: all .3s cubic-bezier(1.0, 0.5, 0.8, 1.0);
}
.logo-link-slide-enter, .logo-link-slide-leave-to {
  opacity: 0;
}


</style>
