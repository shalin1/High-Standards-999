<template>
  <a>
    {{this.text}}
  </a>
</template>

<script>
export default {
  name: 'NavLink',
  props: {
    text: String,
    destination: String
  }
}
</script>

<style lang='scss' scoped>
@import '../stylesheets/variables';
button {
  color: $black;
  border-style: none;
}
</style>
