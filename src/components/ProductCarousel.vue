<template>
  <div>
    <section class='product-carousel-header'>
      <h2 :class="$mq">Shop New Arrivals</h2>
    </section>
    <section class='product-carousel' :class='$mq'>
      <div class='product-carousel-item' :class='$mq' v-for="item of items" v-bind:key="item.id">
        <a href="#"><img :src='item.images[0].src' />
        <div class='item-info' :class="$mq">
          <h3>{{item.title}}</h3>
          <p>${{item.variants[0].price}}</p>
        </div>
        </a>
      </div>
    </section>
  </div>
</template>

<script>
import Client from 'shopify-buy'
const client = Client.buildClient({
  domain: 'highstandards999.myshopify.com',
  storefrontAccessToken: '4774ee906ad074c16eb30a467bc0349c'
})
export default {
  name: 'productCarousel',
  data () {
    return {
      items: [],
      errors: []
    }
  },
  // Fetches posts when the component is created.
  created () {
    client.product.fetchAll().then(products => {
      products.forEach(product => {
        this.items.push(product)
      })
    })
  }
}
</script>

<style lang='scss' scoped>

@import '../stylesheets/variables';
h2 {
  padding: 24px 30px;
  &.lg{
    padding: 24px 10vw;
  }
}
.product-carousel{
  background-color: $light-gray;
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  &.lg{
    flex-wrap:nowrap;
    max-width: 100vw;
  }
}
.product-carousel-item {
  display: flex;
  flex-direction: column;
  border: 1px solid $gray;
  width: 50%;
  overflow: hidden;
  &.lg{
    width: 25%;
  }
}
.item-info{
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: flex-start;
  padding: 0 12px 12px 12px;
  z-index: 10;
  &.lg{
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    padding: 9px 24px 12px 24px;
  }
}
img {
  width: 100%;
  z-index: 1;
  transition: .8s ;

  &:hover{
    transform: scale(1.05);
    transition: .6s ;
  }
}
</style>
