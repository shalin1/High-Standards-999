<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h2>Heading 2</h2>
    <h3>Heading 3</h3>
    <button>Button</button>
    <p>
      This is paragraph text
    </p>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>

  button {
    background: $black;
    padding: 30px;
  }
</style>
