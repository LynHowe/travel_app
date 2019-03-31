<template>
  <div>
    <detail-banner></detail-banner>
    <detail-header></detail-header>
    <div class="content">
      <detail-list :tipList="list"></detail-list>
    </div>
  </div>
</template>

<script>
import DetailBanner from './components/Banner'
import DetailHeader from './components/Header'
import DetailList from './components/List'

export default {
  name: 'Detail',
  components: {
    DetailBanner,
    DetailHeader,
    DetailList
  },
  data () {
    return {
      list: [{
        type: '成人票',
        branch: [{
          type: '成人故宫前庭票',
          branch: [{
            type: '前殿票'
          }, {
            type: '侧殿票'
          }]
        }, {
          type: '成人故宫后宫票'
        }]
      }, {
        type: '学生票',
        branch: [{
          type: '学生故宫前庭票',
          branch: [{
            type: '前殿票'
          }, {
            type: '侧殿票'
          }]
        }, {
          type: '学生故宫后宫票'
        }]
      }, {
        type: '儿童票',
        branch: [{
          type: '学生故宫前庭票',
          branch: [{
            type: '前殿票'
          }, {
            type: '侧殿票'
          }]
        }, {
          type: '学生故宫后宫票'
        }]
      }]
    }
  }
}

</script>

<style lang='stylus' scoped>
  .content
    height: 20rem
</style>
