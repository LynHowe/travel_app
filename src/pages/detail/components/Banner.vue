<template>
  <div class="banner">
    <img class="banner-img" src="//img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_600x330_f922b488.jpg">
    <div class="banner-wrapper">
      <div class="banner-title">故宫(AAAAA景区)</div>
      <div class="banner-number">
        <span class="iconfont banner-icon">&#xe606;</span>
        39
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailBanner',
  data () {
    return {
    }
  }
}

</script>

<style lang='stylus' scoped>
  .banner
    position: relative
    overflow: hidden
    height: 0
    padding-bottom: 50%
    .banner-img
      width:100%
    .banner-wrapper
      display: flex
      position: absolute
      bottom: 0
      left: 0
      right: 0
      color: #fff
      height: .8rem
      line-height: .6rem
      background-image: linear-gradient(top, rgba(0, 0, 0, 0),
      rgba(0, 0, 0, .8))
      .banner-title
        flex: 1
        font-size: .4rem
        margin-left: .25rem
      .banner-number
        float: right
        background: rgba(0, 0, 0, .8)
        margin: 0 .3rem .2rem .3rem
        padding: 0 .35rem
        text-align: center
        border-radius: .3rem
        font-size: .31rem
        .banner-icon
          font-size: .3rem
</style>
