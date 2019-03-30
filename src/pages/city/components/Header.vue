<template>
  <div class="header">
    <router-link to="/">
      <div class="header-left">
        <div class="iconfont back-icon">&#xe624;</div>
      </div>
    </router-link>
    城市选择
  </div>
</template>

<script>
export default {
  name: 'CityHeader',
  data () {
    return {
    }
  }
}

</script>

<style lang='stylus' scoped>
  @import '~@/assets/styles/variable.styl'
  .header
    touch-action: none
    position: relative
    text-align: center
    height: $headerHeight
    background: $bgColor
    line-height: $headerHeight
    font-size: .35rem
    color: #fff
    .header-left
      position: absolute
      width: .64rem
      .back-icon
        text-align: center
        font-size: .4rem
        color: #fff
</style>
