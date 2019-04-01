<template>
  <div>
    <div class="banner" @click="handleGalleryShow">
      <img class="banner-img" :src="bannerImg">
      <div class="banner-wrapper">
        <div class="banner-title">{{sightName}}</div>
        <div class="banner-number">
          <span class="iconfont banner-icon">&#xe606;</span>
          {{gallaryImgs.length}}
        </div>
      </div>
    </div>
    <common-animation>
      <template #animation>
        <common-gallery
          :galleryImgs="gallaryImgs"
          v-show="galleryShow"
          @hidden="handleGalleryHidden"
        ></common-gallery>
      </template>
    </common-animation>
  </div>
</template>

<script>
import CommonGallery from '@/common/gallery/Gallery'
import CommonAnimation from '@/common/animation/Animation'

export default {
  name: 'DetailBanner',
  components: {
    CommonGallery,
    CommonAnimation
  },
  props: {
    sightName: String,
    bannerImg: String,
    gallaryImgs: Array
  },
  data () {
    return {
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
    padding-bottom: 55%
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
