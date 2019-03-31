<template>
  <div>
    <div class="banner" @click="handleGalleryShow">
      <img class="banner-img" src="//img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_600x330_f922b488.jpg">
      <div class="banner-wrapper">
        <div class="banner-title">故宫(AAAAA景区)</div>
        <div class="banner-number">
          <span class="iconfont banner-icon">&#xe606;</span>
          39
        </div>
      </div>
    </div>
    <common-gallery
      :galleryImgs="galleryImgs"
      v-show="galleryShow"
      @hidden="handleGalleryHidden"
    ></common-gallery>
  </div>
</template>

<script>
import CommonGallery from '@/common/gallery/Gallery'

export default {
  name: 'DetailBanner',
  components: {
    CommonGallery
  },
  data () {
    return {
      galleryImgs: ['http://img1.qunarzz.com/sight/p0/201404/23/04b92c99462687fa1ba45c1b5ba4ad77.jpg_800x800_70debc93.jpg',
        'http://img1.qunarzz.com/sight/p0/201404/23/04b92c99462687fa1ba45c1b5ba4ad77.jpg_800x800_70debc93.jpg'],
      galleryShow: false
    }
  },
  methods: {
    handleGalleryShow () {
      this.galleryShow = true
    },
    handleGalleryHidden () {
      this.galleryShow = false
    }
  }
}

</script>

<style lang='stylus' scoped>
  .banner
    touch-action: none
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
      background-image:
      linear-gradient(to bottom,
      rgba(0, 0, 0, 0),
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
