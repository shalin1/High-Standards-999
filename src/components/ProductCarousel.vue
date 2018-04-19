<template>
  <div>
    <section class='product-carousel-header'>
      <h2>Shop New Arrivals</h2>
    </section>
    <section class='product-carousel' :class='$mq'>
      <div class='product-carousel-item' :class='$mq' v-for="item of items" v-bind:key="item.id">
        <img :src='item.images[0].src' />
        <div class='item-info'>
          <h3>{{item.title}}</h3>
          <p>${{item.variants[0].price}}</p>
        </div>
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
  padding: 30px 20px;
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
  flex: 1 0 50vw;
  &.lg{
    flex: 1 0 25vw;
  }
}
.item-info{
  padding: 12px;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: flex-start;
  flex-wrap: wrap;
}
img {
  width: 100%;
}
</style>
