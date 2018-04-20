<template>
  <section class='hero-area' :class="$mq">
    <article class='text-side' :class='$mq'>
      <div class='nav-offset' :class="$mq"></div>
      <h1 class='headline' :class='$mq'>High Standards</h1>
      <h3 :class='$mq'>Low Maintance</h3>
      <p :class='$mq'>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
      </p>
      <div class="swiper-pagination" slot="pagination"></div>
    </article>
    <swiper :options='swiperOption' ref='heroCarousel'>
      <swiper-slide>    <img :class='$mq' src='../assets/carousel-hero.jpg' />
          <button :class='$mq'>Start Shopping</button>
      </swiper-slide>
      <swiper-slide>    <img :class='$mq' src='../assets/carousel-hero.jpg' />
          <button :class='$mq'>Start Shopping</button>
      </swiper-slide>
      <swiper-slide>    <img :class='$mq' src='../assets/carousel-hero.jpg' />
          <button :class='$mq'>Start Shopping</button>
      </swiper-slide>
      <swiper-slide>    <img :class='$mq' src='../assets/carousel-hero.jpg' />
          <button :class='$mq'>Start Shopping</button>
      </swiper-slide>
  </swiper>
  </section>
</template>

<script>
import { swiper, swiperSlide } from 'vue-awesome-swiper'
import 'swiper/dist/css/swiper.css'

export default {
  name: 'HeroArea',
  components: {
    swiper,
    swiperSlide
  },
  data () {
    return {
      swiperOption: {
        autoplay: {
          delay: 2500,
          disableOnInteraction: false
        },
        pagination: {
          el: '.swiper-pagination',
    			clickable: true,
          renderBullet: function (index, className) {
            return '<div class="' + className + '"></div>';
          }
        },
      }
    }
  }
}
</script>

<style lang='scss' scoped>
@import '../stylesheets/variables';

section {
  background-color: $pistachio;
  height: 587px;
  &.lg {
    height: 680px;
  }
}

.nav-offset {
  height: 60px;
  &.lg {
    height: 84px;
  }
}

.hero-area {
  display: flex;
  flex-direction: column;
  &.lg {
    height: 680px;
    flex-direction: row;
  }
}

.text-side {
  background-color: $pistachio;
  padding: 21px 24px 21px 24px;
  color: $black;
  &.lg {
    padding: 113px 10vw 0 10vw;
  }
}

img {
  object-fit: cover;
  object-position: 0 0;
  position: relative;
  display: flex;
  align-items: center;
}

.headline {
  color: $white;
  padding-bottom: 27px;

  &.lg {
    padding-bottom: 40px;
  }
}

h3 {
  padding-bottom: 6px;
  &.lg {
    padding-bottom: 12px;
  }
}

p {
  &.lg {
    padding-right: 10vw;
  }
}
</style>

<style>
.swiper-pagination-bullet {
  margin: 24px 24px 24px 0;
	border-radius: 0;
	width: 5px;
	height: 5px;
	color:#000;
	opacity: 1;
	background: #DDDDDD;
}
.swiper-pagination-bullet-active {
	color:#fff;
	background: #202F2F;
}
</style>
