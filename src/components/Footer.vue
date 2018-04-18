<template>
  <nav class='footer-container'>
    <div v-for="(url,title) in links" :key='url.id'>
      <a :href='url'><h3>{{title}}</h3></a>
    </div>
  </nav>
</template>

<script>
export default {
  name: 'Footer',
  data () {
    return {
      links: {
        'Jobs': '#',
        'Contact': '#',
        'FAQ': '#',
        'Shipping & Returns': '#'
      }
    }
  }
}
</script>

<style lang='scss' scoped>
@import '../stylesheets/variables';
nav {
  background-color: $black;
  border-style: none;
  width: 100vw;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: flex-start;
  flex-wrap: wrap;
  padding: 20px;
  height: 120px;
}
h3{
  color: $white;
  padding: 5px;
}

</style>
