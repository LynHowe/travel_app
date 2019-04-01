<template>
  <div class="icons">
    <swiper :options="swiperOption">
      <swiper-slide v-for="(page, index) of pages" :key="index">
        <div
          class="icon-border"
          v-for="item of page"
          :key="item.id"
        >
          <div class="icon">
            <img class="icon-img" :src="item.imgUrl">
          </div>
          <p class="icon-desc">{{item.desc}}</p>
        </div>
      </swiper-slide>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeIcons',
  props: {
    list: Array
  },
  data () {
    return {
      swiperOption: {
        autopaly: false
      }
    }
  },
  computed: {
    pages () {
      const pages = []
      this.list.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>

<style lang='stylus' scoped>
  @import '~@/assets/styles/variable.styl'
  @import '~@/assets/styles/mixins.styl'
  .icons >>> .swiper-container
    height: 0
    padding-bottom: 50%
  .icons
    margin: .1rem 0
    touch-action: pan-y
    .icon-border
      position: relative
      float: left
      overflow: hidden
      height: 0
      width: 25%
      padding-bottom: 25%
      .icon
        position: absolute
        top: 0
        left: 0
        right: 0
        bottom: .5rem
        box-sizing: border-box
        padding: .05rem
        .icon-img
          height: 100%
          display: block
          margin: 0 auto
      .icon-desc
        color: $iconNameColor
        position: absolute
        bottom: 0
        left: 0
        right: 0
        height .5rem
        line-height: .5rem
        text-align: center
        padding-bottom: .05rem
        ellipsis()
</style>
