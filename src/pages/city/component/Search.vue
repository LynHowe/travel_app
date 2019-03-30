<template>
  <div ref="">
    <div class="search">
      <input
        type="text"
        class="search-input"
        placeholder="输入城市名或名称"
        v-model="keyword"
      >
    </div>
    <div class="search-list" ref="search" v-show="keyword">
      <ul>
        <li
          class="search-item border-bottom"
          v-for="item of list"
          :key="item.id"
          @click="handleCityChange(item.name)"
        >
          {{item.name}}
        </li>
        <li class="search-item border-bottom" v-show="show">
          没有找到匹配的城市信息
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import BScroll from 'better-scroll'

export default {
  name: 'CitySearch',
  props: {
    cities: Object
  },
  data () {
    return {
      keyword: '',
      list: [],
      timer: null
    }
  },
  computed: {
    show () {
      return !this.list.length
    }
  },
  methods: {
    handleCityChange (city) {
      this.$store.commit('changeCity', city)
      this.$router.push('/')
    }
  },
  watch: {
    keyword () {
      if (this.timer) {
        clearTimeout(this.timer)
      }
      if (!this.keyword) {
        this.list = []
        return
      }
      this.timer = setTimeout(() => {
        const result = []
        for (let i in this.cities) {
          this.cities[i].forEach((value) => {
            if (value.spell.indexOf(this.keyword) > -1 ||
              value.name.indexOf(this.keyword) > -1) {
              result.push(value)
            }
          })
        }
        this.list = result
      }, 100)
    }
  },
  mounted () {
    this.scroll = new BScroll(this.$refs.search)
  }
}
</script>

<style lang='stylus' scoped>
  @import '~@/assets/styles/variable.styl'
  .search
    margin-top: -.02rem
    padding: 0 .36rem .1rem .2rem
    background: $bgColor
    height: .7rem
    .search-input
      text-align: center
      height: .67rem
      margin: auto
      width: 100%
      border-radius: .1rem
      box-sizing: border-box
      padding: .2rem
      color: #666
  .search-list
    background: #eee
    position: absolute
    overflow: hidden
    bottom: 0
    left: 0
    right: 0
    top: 1.58rem
    z-index: 1
    .search-item
      line-height: .76rem
      padding-left: .2rem
      background: #fff
      color: #666
</style>
