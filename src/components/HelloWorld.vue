<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h2>Heading 2</h2>
    <h3>Heading 3</h3>
    <FooterButton label='footer button'></FooterButton>

      <HeaderButton label='header button'></HeaderButton>

    <p>This is paragraph text</p>
  </div>
</template>

<script>
import FooterButton from './FooterButton.vue'
import HeaderButton from './HeaderButton.vue'

export default {
  name: 'HelloWorld',
  components: {
    FooterButton,
    HeaderButton
  },
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang='scss' scoped>
@import '../stylesheets/variables';

.hello {
  background: $pistachio;
}
.hello * {
  padding: 20px;
  margin: 20px;
}
</style>
