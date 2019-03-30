<template>
  <div>
    <city-header></city-header>
    <city-search :cities="cities"></city-search>
    <city-list
      :hot="hotCities"
      :cities="cities"
      :alphabet="alphabet"
    ></city-list>
    <city-alphabet
      :cities="cities"
      @change="handleAlphabetChange"
    ></city-alphabet>
  </div>
</template>

<script>
import CityHeader from './components/Header'
import CitySearch from './components/Search'
import CityList from './components/List'
import CityAlphabet from './components/Alphabet'
import axios from 'axios'

export default {
  name: 'City',
  components: {
    CityHeader,
    CitySearch,
    CityList,
    CityAlphabet
  },
  data () {
    return {
      hotCities: [],
      cities: {},
      alphabet: ''
    }
  },
  methods: {
    handleAlphabetChange (e) {
      this.alphabet = e
    },
    getCityInfo () {
      axios.get('https://easy-mock.com/mock/5c9dfe43fcc8741fc1eba4ee/api/cityinfo')
        .then(this.getCityInfosucc)
    },
    getCityInfosucc (res) {
      res = res.data
      if (res.ret && res.data) {
        const data = res.data
        this.hotCities = data.hotCities
        this.cities = data.cities
      }
    }
  },
  mounted () {
    return this.getCityInfo()
  }
}

</script>

<style lang='stylus' scoped>
</style>
