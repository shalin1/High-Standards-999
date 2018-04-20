<template>
  <section class='hero-area' :class="$mq">
    <article class='text-side' :class='$mq'>
      <section class='nav-offset' :class="$mq"></section>
      <h1 class='headline' :class='$mq'>High Standards</h1>
      <h3 :class='$mq'>Low Maintance</h3>
      <p :class='$mq'>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
      </p>
      <section class="swiper-pagination" slot="pagination"></section>
    </article>
      <swiper  :class='$mq' :options='swiperOption' ref='heroCarousel'>
        <swiper-slide :style='$mq'></swiper-slide>
        <swiper-slide :style='$mq'></swiper-slide>
        <swiper-slide :style='$mq'></swiper-slide>
        <swiper-slide :style='$mq'></swiper-slide>
      </swiper>
      <a href='#'><div class='hero-label' :class='$mq'><h3 :class='$mq'>Start Shopping</h3></div></a>
  </section>
</template>

<script>
import { swiper, swiperSlide } from 'vue-awesome-swiper'
import '../stylesheets/swiper.css'

export default {
  name: 'HeroArea',
  components: {
    swiper,
    swiperSlide
  },
  data() {
    return {
      swiperOption: {
        slidesPerView: 1,
        autoplay: {
          delay: 5000,

          disableOnInteraction: false
        },
        speed: 800,
        pagination: {
          el: '.swiper-pagination',
          clickable: true,
          renderBullet: function(index, className) {
            return '<div class="' + className + '"></div>'
          }
        }
      }
    }
  }
}
</script>

<style lang='scss' scoped>
@import '../stylesheets/variables';

.nav-offset {
  height: 60px;
  &.lg {
    height: 84px;
  }
}

.hero-area {
  background-color: $pistachio;
  display: flex;
  flex-direction: column;
  position: relative;
  &.lg {
    height: 680px;
    flex-direction: row;
  }
}

.hero-label {
  width: calc(50vw - 5px);
  height: 60px;
  color: $white;
  background-color: $black;
  position: absolute;
  bottom: 0;
  right: 0;
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 100;

  &.lg {
    width: 25vw;
    height: 84px;
  }
  & h3 {
    padding-bottom: 38px;
    color: $white;
    transition: 1s;
    &:hover {
      color: $pistachio;
      transition: 1s;
    }
    &.lg {
      padding: 0;
    }
  }
}

.text-side {
  background-color: $pistachio;
  padding: 21px 24px 20px 24px;
  color: $black;
  &.lg {
    padding: 113px 0 0 10vw;
    width: 866px;
    min-width: 614px;
  }
}

// .carousel-container{
//   position: relative;
// }
.swiper-slide {
  background-image: url('../assets/carousel-hero.jpg');
  background-size: cover;
  background-position: center;
  &.lg {
    width: 100vw;
  }
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
div {
  width: 100vw;
}
@media only screen and (max-width: 900px) {
  div {
    height: 294px;
    padding-top: 40px;
    background-size: cover;
  }
}
</style>
<style>
.swiper-pagination-bullet {
  margin: 24px 24px 24px 0;
  border-radius: 0;
  width: 6px;
  height: 6px;
  color: #000;
  opacity: 1;
  background: #dddddd;
}
.swiper-pagination-bullet-active {
  color: #fff;
  background: #202f2f;
}
</style>
