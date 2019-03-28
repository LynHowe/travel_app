<template>
  <div>
    <div class="recommend-header">热门推荐</div>
    <ul>
      <li
        class="item-wrapper border-bottom"
        v-for="item of recommendList"
        :key="item.id"
      >
        <img class="item-img" :src="item.imgUrl">
        <div class="item-content">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
          <button class="item-btn">查看详情</button>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  data () {
    return {
      recommendList: [{
        id: '001',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1707/fb/fb0f814e1be3312a3.water.jpg_200x200_47548f58.jpg',
        title: '自然之门',
        desc: '浪漫的大连首站，浪漫的海洋注意乐园'
      }, {
        id: '002',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1603/3b/3b0a34d3984b4ac590.water.jpg_200x200_4fa25893.jpg',
        title: '南澳岛',
        desc: '风景秀丽，海鲜种类众多，环境优美，海天一色'
      }, {
        id: '003',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1512/62/628c1e85c1d00e3590.water.jpg_200x200_cf118541.jpg',
        title: '丹樱生态园',
        desc: '百花盛开，鸟语花香，富有林园气息，恬静悠然'
      }]
    }
  }
}

</script>

<style lang='stylus' scoped>
  @import '~@/assets/styles/mixins.styl'
  .recommend-header
    background: #eee
    height: .6rem
    text-indent: .2rem
    line-height: .6rem
  .item-wrapper
    display: flex
    height: 2.4rem
    .item-img
      width: 2.2rem
      height: 2.2rem
      margin: .1rem
    .item-content
      flex: 1
      padding: .2rem
      min-width: 0
      .item-title
        line-height: .5rem
        font-size: .34rem
        ellipsis()
      .item-desc
        line-height: .7rem
        font-size: .32rem
        color: #888
        ellipsis()
      .item-btn
        color: #fff
        margin-top: .25rem
        padding: 0 .1rem
        line-height: .5rem
        background: #ff9300
        border-radius: .05rem
</style>
