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
  background-color: rgba(32, 47, 47, 0.0);
  color: $black;
  border-style: none;
}
</style>
