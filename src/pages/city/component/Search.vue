<template>
  <div class="search">
    <input type="text" class="search-input" placeholder="输入城市名或名称">
  </div>
</template>

<script>
export default {
  name: 'CitySearch'
}
</script>

<style lang='stylus' scoped>
  @import '~@/assets/styles/variable.styl'
  .search
    margin-top: -.02rem
    padding: 0 .36rem .1rem .2rem
    background: $bgColor
    height: .7rem
    .search-input
      text-align: center
      height: .67rem
      margin: auto
      width: 100%
      border-radius: .1rem
      box-sizing: border-box
      padding: .2rem
      color: #666
</style>
