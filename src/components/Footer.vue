<template>
  <nav class='footer-container' :class="$mq">
      <div v-for="(url,title) in links" :key='url.id' :class="$mq" class='link-container'>
        <a :href='url'><h3 :class="$mq">{{title}}</h3></a>
      </div>
  </nav>
</template>

<script>
export default {
  name: 'Footer',
  data() {
    return {
      links: {
        Jobs: '#',
        Contact: '#',
        FAQ: '#',
        'Shipping & Returns': '#'
      }
    }
  }
}
</script>

<style lang='scss' scoped>
@import '../stylesheets/variables';

.footer-container {
  background-color: $black;
  border-style: none;
  width: 100vw;
  display: flex;
  align-items: flex-start;
  height: 120px;
  flex-direction: column;
  flex-wrap: wrap;
  justify-content: flex-start;
  &.lg {
    align-items: center;
    height: 84px;
    padding-left: 142px;
    flex-direction: row;
    flex-wrap: nowrap;
  }
}
h3 {
  color: $white;
  transition: 1s;
  padding: 24px 24px 0 24px;
  &.lg {
    padding: 30px 78px 30px 0;
  }
  &:hover {
    transition: 1s;
    color: $pistachio;
  }
}

.link-container {
  // padding:
}
</style>
