<template>
  <div>
    <div
      v-for="(item, index) of list"
      :key="index"
      class="list border-bottom"
    >
      <div class="tip">
        <span class="icon"></span>
        {{item.type}}
      </div>
      <div v-if="item.branch" class="list-child">
        <detail-list :list="item.branch"></detail-list>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailList',
  props: {
    list: Array
  }
}

</script>

<style lang='stylus' scoped>
  .tip
    line-height: .8rem
    padding: 0 .2rem
    font-size: .28rem
    .icon
      display: inline-block
      position: relative
      width: .36rem
      height: .36rem
      top: .08rem
      left: .18rem
      background: url(//s.qunarzz.com/piao/image/touch/sight/detail.png) 0 -.9rem no-repeat
      margin-right: .1rem
      background-size: .4rem 3rem
  .list-child
    padding: 0 .3rem
</style>
