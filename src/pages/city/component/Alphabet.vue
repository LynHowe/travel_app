<template>
  <ul class="list">
    <li
      class="item"
      v-for="(item, key) of cities"
      :key="key"
    >{{key}}</li>
  </ul>
</template>

<script>
export default {
  name: 'CityAlphabet',
  props: {
    cities: Object
  }
}

</script>

<style lang='stylus' scoped>
  @import '~@/assets/styles/variable.styl'
  .list
    width: .46rem
    position: absolute
    right: 0
    bottom: 0
    top: 1.58rem
    display: flex
    flex-direction: column
    justify-content: center
    .item
      line-height: .44rem
      color: $bgColor
      text-align: center
</style>
