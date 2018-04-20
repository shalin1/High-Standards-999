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
      <transition name='fade' mode='out-in'>
          <div v-if='showMobileLinks' class='mobile-links'>
            <a  v-for='(url,title) in links' :key='url.id' href='url'><h3 class='mobile-link'>{{title}}</h3></a>
          </div>
          <a v-else href='/'><img class='logo' src='../../assets/logo.png' /></a>
        </transition>
        <transition name='fade' mode='out-in'>
          <Cart />
        </transition>
      </nav>
    </mq-layout>

    <mq-layout mq="lg">
      <nav class='header-container lg'>
        <div>
          <a href='/'><img class='logo' src='../../assets/logo.png' /></a>
          <ul>
            <a v-for='(url,title) in links' :key='url.id'  :href='url'>
              <li><h3>{{title}}</h3></li>
            </a>
          </ul>
        </div>
        <Cart />
      </nav>
    </mq-layout>

  </div>
</template>

<script>
import Cart from './Cart.vue'
import Hamburger from './Hamburger.vue'

export default {
  name: 'Header',
  props: {
    label: String
  },
  components: {
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
  &.inverted {
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
.x {
  color: $white;
  padding-right: 2vw;
}
.logo {
  color: $black;
  transition: 1s;
  filter: invert(100%);
  height: 36px;
  width: 36px;
  margin-left: 10px;
  &:hover {
    transition: 1s;
    filter: invert(75%);
  }
}
li {
  display: block;
  padding: 30px 39px;
  transition: 5s;
  &:hover {
    transition: 0.5s;
    background-color: $pistachio;
  }
}
ul {
  display: flex;
  flex-direction: row;
  padding-left: 39px;
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
.mobile-link {
  padding: 0 5vw;
  color: $white;
}
.fade-enter-active {
  transition: all 0.3s cubic-bezier(1, 0.5, 0.8, 1);
}
.fade-leave-active {
  transition: all 0.3s cubic-bezier(1, 0.5, 0.8, 1);
}
.fade-enter,
.fade-leave-to {
  opacity: 0;
}
</style>
