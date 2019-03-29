<template>
  <div>
    <div class="weekend-header">周末去哪儿</div>
    <ul>
      <li v-for="item of list" :key="item.id">
        <div class="item-img-wrapper">
          <img class="item-img" :src="item.imgUrl">
        </div>
        <div class="item-content">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeWeekend',
  props: {
    list: Array
  }
}

</script>

<style lang='stylus' scoped>
  @import '~@/assets/styles/mixins.styl'
  .weekend-header
    height: .6rem
    background: #eee
    text-indent: .2rem
    line-height : .6rem
  .item-img-wrapper
    background: blue
    height: 0
    width: 100%
    padding-bottom: 36%
    overflow: heddien
    .item-img
      width: 100%
  .item-content
    padding: .2rem
    min-width: 0
    .item-title
      line-height: .5rem
      font-size: .34rem
      ellipsis()
    .item-desc
      line-height: .7rem
      font-size: .32rem
      width: 6rem
      color: #888
      ellipsis()
</style>
