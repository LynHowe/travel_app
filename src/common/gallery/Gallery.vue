<template>
  <div class="gallery" @click="handleGalleryhidden">
    <div class="img-wrapper">
      <swiper  :options="swiperOption">
        <swiper-slide
          v-for="(item, index) of galleryImgs"
          :key="index"
        >
          <img class="img" :src="item">
        </swiper-slide>
        <div class="swiper-pagination"  slot="pagination"></div>
      </swiper>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CommonGallery',
  props: {
    galleryImgs: {
      type: Array,
      default () {
        return []
      }
    }
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        paginationType: 'fraction',
        observeParents: true,
        observer: true
      }
    }
  },
  methods: {
    handleGalleryhidden () {
      this.$emit('hidden')
    }
  }
}

</script>

<style lang='stylus' scoped>
  .gallery >>> .swiper-container
    overflow: visible
  .gallery
    touch-action: none
    position: fixed
    top: 0
    left: 0
    right: 0
    bottom: 0
    z-index: 99
    background: #000
    display: flex
    flex-direction: column
    justify-content: center
    .img-wrapper
      background: #ccc
      height: 0
      padding-bottom: 100%
      .img
        width: 100%
    .swiper-pagination
      bottom: -1.5rem
      color: #fff
</style>
