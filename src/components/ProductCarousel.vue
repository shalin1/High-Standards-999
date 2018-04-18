<template>
  <div>

  <section class='product-carousel-header'>
    <h2>Shop New Arrivals</h2>
  </section>
  <section class='product-carousel'>
    <li v-for="item of items" v-bind:key="item.id">
      {{item.title}}
    </li>
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
</style>
