<template>
  <div>
    <div class="btn" v-show="showHeader" @click="removeEvent">
      <div class="iconfont btn-back">&#xe624;</div>
    </div>
    <div
      class="header"
      v-show="!showHeader"
      :style="opacityStyle"
    >
      <div class="icon-wrapper">
        <div
          class="iconfont icon-back"
          @click="removeEvent"
        >&#xe624;</div>
      </div>
      <div class="header-title">景点详情</div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailHeader',
  data () {
    return {
      showHeader: true,
      opacityStyle: {
        opacity: 0
      }
    }
  },
  methods: {
    handleScroll () {
      const top = document.documentElement.scrollTop
      if (top > 40) {
        let opacity = top / 140
        opacity = opacity > 1 ? 1 : opacity
        this.opacityStyle = { opacity }
        this.showHeader = false
      } else {
        this.showHeader = true
      }
    },
    removeEvent () {
      window.removeEventListener('scroll', this.handleScroll)
      this.$router.push('/')
    }
  },
  mounted () {
    window.addEventListener('scroll', this.handleScroll)
  }
}

</script>

<style lang='stylus' scoped>
  @import '~@/assets/styles/variable.styl'
  @import '~@/assets/styles/mixins.styl'
  .btn
    position: absolute
    left: .2rem
    top: .1rem
    height: .65rem
    width: .65rem
    border-radius: .4rem
    background: rgba(0, 0, 0, .8)
    line-height: .65rem
    .btn-back
      color: #fff
      text-align: center
      font-size: .4rem
  .header
    z-index: 2
    touch-action: none
    position: fixed
    top: 0
    left: 0
    right: 0
    text-align: center
    height: $headerHeight
    background: $bgColor
    line-height: $headerHeight
    font-size: .35rem
    color: #fff
    .icon-wrapper
      position: absolute
      width: .64rem
      .icon-back
        text-align: center
        font-size: .4rem
        color: #fff
</style>
