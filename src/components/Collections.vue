<template>
  <div class='collections-container' :class='$mq'>
    <section class='collections-text' :class='$mq'>
      <h2>Collections</h2>
      <p>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
      </p>
      <svg class='arrow' v-on:click='swiper.slidePrev(500, false)' width="12px" height="12px" viewBox="0 0 12 12" version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
        <g id="desktop_home" transform="translate(-149.000000, -1742.000000)" fill="#202F2F">
          <g id="Collections" transform="translate(1.000000, 1244.000000)">
            <g id="Arrows" transform="translate(142.000000, 492.000000)">
              <g id="left-arrow">
                <polygon id="Shape" points="12 6 13.0575 7.0575 8.8725 11.25 18 11.25 18 12.75 8.8725 12.75 13.0575 16.9425 12 18 6 12"></polygon>
              </g>
            </g>
          </g>
        </g>
      </svg>
      <svg class='arrow' v-on:click='swiper.slideTo(swiper.activeIndex < 2 ? swiper.activeIndex+1 : 0,500, false)' width="12px" height="12px" viewBox="0 0 12 12" version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
        <g id="desktop_home" transform="translate(-185.000000, -1742.000000)" fill="#202F2F">
          <g id="Collections" transform="translate(1.000000, 1244.000000)">
            <g id="Arrows" transform="translate(142.000000, 492.000000)">
              <g id="right-arrow" transform="translate(36.000000, 0.000000)">
                <polygon id="Shape" points="12 6 10.9425 7.0575 15.1275 11.25 6 11.25 6 12.75 15.1275 12.75 10.9425 16.9425 12 18 18 12"></polygon>
              </g>
            </g>
          </g>
        </g>
      </svg>

    </section>
      <swiper class='collections-carousel' :class='$mq' :options='swiperOption' ref='categoriesCarousel'>
        <swiper-slide :class='$mq' v-for='item of items' v-bind:key='item.id'>
          <img v-if='item.title!==","' :src='item.image.src' />
          <div class='category-label'>
            <h3 v-if='item.title!==","'>{{item.title}}</h3>
          </div>
        </swiper-slide>
      </swiper>
  </div>
</template>

<script>
import { swiper, swiperSlide } from 'vue-awesome-swiper'
import 'swiper/dist/css/swiper.css'
import Client from 'shopify-buy'
const client = Client.buildClient({
  domain: 'highstandards999.myshopify.com',
  storefrontAccessToken: '4774ee906ad074c16eb30a467bc0349c'
})

export default {
  name: 'productCarousel',
  components: {
    swiper,
    swiperSlide
  },
  data () {
    return {
      swiperOption: {
        slidesPerView: 'auto',
        spaceBetween: 24,
        navigation: {
          nextEl: '.swiper-button-next',
          prevEl: '.swiper-button-prev'
        }
      },
      items: [],
      errors: []
    }
  },
  // Fetches posts when the component is created.
  created () {
    client.collection.fetchAll().then(collections => {
      collections.forEach(collection => {
        this.items.push(collection)
      })
    })
  },
  computed: {
    swiper () {
      return this.$refs.categoriesCarousel.swiper
    }
  },
  mounted () {
    this.swiper.slideTo(0, 2000, false)
  }
}
</script>

<style lang='scss' scoped>
@import '../stylesheets/variables';

.collections-container {
  display: flex;
  flex-direction: column;
  padding-bottom: 30px;
  &.lg {
    flex-direction: row;
  }
}
.collections-text {
  padding: 30px 24px 24px 24px;
  &.lg {
    padding: calc(132px + 10vw) 10vw 0 9.5vw;
    width: 45vw;
  }
}
h2 {
  padding-bottom: 12px;
}
.collections-carousel {
  padding-left: 24px;
  width: 100vw;
  &.lg {
    width: 62.4vw;
    padding: 84px 0;
  }
}
img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  object-position: 0 50%;
  position: relative;
  display: flex;
  align-items: center;
}

.swiper-slide {
  width: 239px;
  height: 348px;
  &.lg{
    width: 330px;
    height: 480px;
  }

  &-active div {
    transition: background-color .5s;
    background-color: $transparent-black;
  }
}

.arrow {
  padding: 24px 12px 0 6px;
}

.category-label {
  width: 100%;
  height: 60px;
  color: white;
  transition: background-color .5s;
  background-color: $transparent;
  position: absolute;
  bottom: 0;
  padding-left: 24px;
  display: flex;
  align-items: center;
}

h3 {
  color: $white;
}
</style>
