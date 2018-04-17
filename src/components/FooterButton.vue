<template>
  <button>{{ label }}</button>
</template>

<script>
export default {
  name: 'FooterButton',
  props: {
    label: String
  }
}
</script>

<style lang='scss' scoped>
@import '../stylesheets/variables';
button {
  background-color: $black;
  color: $white;
}
</style>
