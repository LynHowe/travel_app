<template>
  <ul class="list">
    <li class="item">A</li>
    <li class="item">B</li>
    <li class="item">C</li>
    <li class="item">D</li>
    <li class="item">E</li>
    <li class="item">F</li>
    <li class="item">G</li>
  </ul>
</template>

<script>
export default {
  name: 'CityAlphabet'
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
</style>
