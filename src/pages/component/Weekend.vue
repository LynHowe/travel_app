<template>
  <div>
    <div class="weekend-header">周末去哪儿</div>
    <ul>
      <li v-for="item of weekendList" :key="item.id">
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
  data () {
    return {
      weekendList: [{
        id: '001',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1811/15/66f14e0fd6fbb.jpg_r_640x214_5d69f21d.jpg',
        title: '清远周边逛',
        desc: '人人都有一双发现美的眼睛'
      }, {
        id: '002',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1811/b8/5d599bbdcf8b57.jpg_r_640x214_2ee055e3.jpg',
        title: '浮在海上的绿洲',
        desc: '南海滨海之城，避寒胜地，有温暖的阳光，海风习习'
      }, {
        id: '003',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1505/bc/7aefc32e7f855a.jpg_r_640x214_f88989f3.jpg',
        title: '南沙湾',
        desc: '海滨城市，美食之乡'
      }]
    }
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
