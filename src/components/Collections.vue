<template>
  <div>

  <section>
    <h2>Collections</h2>
    <p>
      Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
    </p>
  </section>
  <section class='collections-carousel'>
    <div v-for="item of items" v-bind:key="item.id">
      <img :src='item.image.src'  />
      <button><h3>{{item.title}}</h3></button>
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
    client.collection.fetchAll().then(collections => {
      collections.forEach(collection => {
        this.items.push(collection)
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
