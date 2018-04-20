<template>
  <div class='collections-container' :class='$mq'>
    <section class='collections-text' :class='$mq'>
      <h2>Collections</h2>
      <p>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
      </p>
      <svg v-on:click='swiper.slideTo(swiper.activeIndex-1, 500, false)' width="12px" height="12px" viewBox="0 0 12 12" version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
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
      <svg v-on:click='swiper.slideTo(swiper.activeIndex+1, 500, false)' width="12px" height="12px" viewBox="0 0 12 12" version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
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
        <swiper-slide v-for='item of items' v-bind:key='item.id'><img :src='item.image.src' /> </swiper-slide>
      </swiper>
      <!-- </swiper><div v-for="item of items" v-bind:key="item.id">
        <img :src='item.image.src'  />
        <button><h3>{{item.title}}</h3></button> -->
  </div>
</template>

<script>
import { swiper, swiperSlide } from 'vue-awesome-swiper'
import '../stylesheets/swiper.css'
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
        slidesPerView:'auto',
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
  &.lg {
    flex-direction: row;
  }
}
.collections-text {
  padding: 30px 24px 24px 24px;
  &.lg {
    padding: 276px 0vw 276px 10vw;
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
    width: 60vw;
    padding: 84px;
  }
}
img {
  width: 330px;
  height: 480px;
  object-fit: cover;
  object-position: 0 50%;
}

.swiper-slide {
  width: 330px;
  height: 480px;
}

</style>
