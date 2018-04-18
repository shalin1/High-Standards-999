<template>
  <button>{{ label }}</button>
</template>

<script>
export default {
  name: 'NavLink',
  props: {
    label: String
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
