<template>
  <ul class="list">
    <li
      class="item"
      v-for="item of letters"
      :key="item"
      :ref="item"
      @click="handleAlphabetClick"
      @touchstart="handleTouchStart"
      @touchmove="handleTouchMove"
      @touchend="handleTouchEnd"
    >{{item}}</li>
  </ul>
</template>

<script>
export default {
  name: 'CityAlphabet',
  props: {
    cities: Object
  },
  data () {
    return {
      touchState: false,
      startY: 0,
      timer: null
    }
  },
  updated () {
    this.startY = this.$refs['A'][0].offsetTop
  },
  computed: {
    letters () {
      const letters = []
      for (let i in this.cities) {
        letters.push(i)
      }
      return letters
    }
  },
  methods: {
    handleAlphabetClick (e) {
      this.$emit('change', e.target.innerText)
    },
    handleTouchStart () {
      this.touchState = true
    },
    handleTouchMove (e) {
      if (this.touchState) {
        if (this.timer) {
          clearTimeout(this.time)
        }
        this.timer = setTimeout(() => {
          const touchY = e.touches[0].clientY - 79
          const index = Math.floor((touchY - this.startY) / 22)
          if (index >= 0 && index < this.letters.length) {
            this.$emit('change', this.letters[index])
          }
        }, 16)
      }
    },
    handleTouchEnd () {
      this.touchState = false
    }
  }
}

</script>

<style lang='stylus' scoped>
  @import '~@/assets/styles/variable.styl'
  .list
    width: .46rem
    position: absolute
    right: 0
    bottom: 0
    top: 1.58rem
    display: flex
    flex-direction: column
    justify-content: center
    .item
      line-height: .3rem
      color: $bgColor
      text-align: center
</style>
