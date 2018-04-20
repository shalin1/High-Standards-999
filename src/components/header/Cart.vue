<template>
  <svg :class='$mq' id='cart' width="20px" height="17px" viewBox="0 0 20 17" version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
      <!-- Generator: Sketch 49.3 (51167) - http://www.bohemiancoding.com/sketch -->
      <defs></defs>
      <g id="Page-1" stroke="none" stroke-width="1" fill="none" fill-rule="evenodd">
          <g id="mobile_home" transform="translate(-336.000000, -42.000000)" fill="#202F2F">
              <g id="Nav" transform="translate(1.000000, 0.000000)">
                  <g id="Icon:-Cart" transform="translate(315.000000, 20.000000)">
                      <path d="M30.5958904,22.3761855 L34.5189673,28.251844 L38.8092729,28.251844 C39.3018967,28.251844 39.7049526,28.6548999 39.7049526,29.1475237 L39.6780822,29.3893572 L37.4030558,37.6923077 C37.1880927,38.4446786 36.4984194,39 35.6743941,39 L24.0305585,39 C23.2065332,39 22.5168599,38.4446786 22.3108535,37.6923077 L20.0358272,29.3893572 C20.0089568,29.308746 20,29.2281349 20,29.1475237 C20,28.6548999 20.4030558,28.251844 20.8956797,28.251844 L25.1859852,28.251844 L29.1090622,22.3851423 C29.2792413,22.1253952 29.5658588,22 29.8524763,22 C30.1390938,22 30.4257113,22.1253952 30.5958904,22.3761855 Z M29.8524763,25.3108535 L27.1654373,29.251844 L32.5395153,29.251844 L29.8524763,25.3108535 Z" id="Combined-Shape"></path>
                  </g>
              </g>
          </g>
      </g>
  </svg>
</template>

<script>
export default {
  name: 'Cart',
}
</script>

<style lang='scss' scoped>
#cart{
  width: 19.7px;
  padding-right: 15px;
  &.lg{
    padding-right: 40px;
  }
}
.inverted {
  fill: #FFFFFF;
}
</style>
