<template>
  <div>
    <div class="recommend-header">热门推荐</div>
    <ul>
      <li
        class="item-wrapper border-bottom"
        v-for="item of list"
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
  props: {
    list: Array
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
