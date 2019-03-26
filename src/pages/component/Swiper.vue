<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
      <swiper-slide v-for="item of swiperList" :key="item.id">
        <img class="swiper-img" :src="item.imgUrl">
      </swiper-slide>
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true,
        autoplay: 4000
      },
      swiperList: [{
        id: '001',
        imgUrl: `https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20193/09f61cf63d5c9eb402a686440b885dc8.jpg_890x330_1acb9da5.jpg`
      }, {
        id: '002',
        imgUrl: `https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20193/3e54fa2d7c6e083ec8dad4ff78423ee6.jpg_890x330_d308c224.jpg`
      }]
    }
  }
}

</script>

<style lang='stylus' scoped>
  .wrapper >>> .swiper-pagination-bullet-active
    background: #fff
  .wrapper
    width: 100%
    height: 0
    overflow: hidden
    padding-bottom: 37.07%
    background: #ccc
    .swiper-img
      width: 100%
</style>
