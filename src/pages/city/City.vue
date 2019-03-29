<template>
  <div>
    <city-header></city-header>
    <city-search></city-search>
    <city-list
      :hot="hotCities"
      :cities="cities"
      :alphabet="alphabet"
    >
    </city-list>
    <city-alphabet
    :cities="cities"
    @change="handleAlphabetChange"
    >
    </city-alphabet>
  </div>
</template>

<script>
import CityHeader from './component/Header'
import CitySearch from './component/Search'
import CityList from './component/List'
import CityAlphabet from './component/Alphabet'
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
    },
    handleAlphabetChange (e) {
      this.alphabet = e
    }
  },
  mounted () {
    return this.getCityInfo()
  }
}

</script>

<style lang='stylus' scoped>
</style>
