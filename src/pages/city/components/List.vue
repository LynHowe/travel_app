<template>
  <div class="list" ref="wrapper">
    <div>
      <div class="area">
        <div class="title border-topbottom">当前城市</div>
        <div class="btn-list">
          <div class="btn-wrapper">
            <div class="btn">{{this.listCity}}</div>
          </div>
        </div>
      </div>
      <div class="area">
        <div class="title border-topbottom">热门城市</div>
                <div class="btn-list">
          <div
            class="btn-wrapper"
            v-for="item of hot"
            :key="item.id"
            @click="handleCityChange(item.name)"
          >
            <div class="btn">{{item.name}}</div>
          </div>
        </div>
      </div>
      <div class="area"
        v-for="(item, key) of cities"
        :key="key"
        :ref="key"
      >
        <div class="title border-topbottom">{{key}}</div>
        <div class="item-list">
          <div
            class="item border-bottom"
            v-for="city of item"
            :key="city.id"
            @click="handleCityChange(city.name)"
          >{{city.name}}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import BScroll from 'better-scroll'
import { mapState, mapMutations } from 'vuex'

export default {
  name: 'CityList',
  props: {
    hot: Array,
    cities: Object,
    alphabet: String
  },
  computed: {
    ...mapState({
      listCity: 'city'
    })
  },
  methods: {
    ...mapMutations(['changeCity']),
    handleCityChange (city) {
      this.changeCity(city)
      this.$router.push('/')
    }
  },
  watch: {
    alphabet () {
      const element = this.$refs[this.alphabet][0]
      this.scroll.scrollToElement(element)
    }
  },
  mounted () {
    this.scroll = new BScroll(this.$refs.wrapper, {
      click: true
    })
  }
}

</script>

<style lang='stylus' scoped>
  .border-topbottom
    &:before
      border-color: #ccc
    &:after
      border-color: #ccc
  .border-bottom
    &:before
      border-color: #ccc
  .list
    overflow: hidden
    position: absolute
    top: 1.58rem
    left: 0
    right: 0
    bottom: 0
    .title
      line-height: .54rem
      background: #eee
      padding-left: .2rem
      color: #666
      font-size: .26rem
    .btn-list
      overflow: hidden
      padding: .1rem
      padding: .1rem .6rem .1rem .1rem
      .btn-wrapper
        float: left
        width: 33.33%
        .btn
          margin: .1rem
          padding: .1rem 0
          text-align: center
          border: .02rem solid #ccc
          border-radius: .06rem
    .item
      line-height: .76rem
      padding-left: .2rem
      color: #666
      background: #fff
</style>
