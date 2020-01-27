<template>
  <div>
    <city-header></city-header>
    <city-search></city-search>
    <city-list :cities="cities" :hot="hotCities" :letter="letter"></city-list>
    <city-alphabet :cities="cities"
                    @change="handleLetterChange"></city-alphabet>
  </div>
</template>

<script>
import axios from 'axios'
import CityHeader from './commponents/Header'
import CitySearch from './commponents/Search'
import CityList from './commponents/List'
import CityAlphabet from './commponents/Alphabet'

export default {
  name: 'City',
  data() {
    return {
      cities: {},
      hotCities: [],
      letter: ''
    }
  },
  mounted() {
    this._getCityInfo()
  },
  methods: {
    handleLetterChange(letter) {
      this.letter = letter
    },
    _getCityInfo() {
      axios.get('/api/city.json')
        .then(this._handleGetCityInfoSucc)
    },
    _handleGetCityInfoSucc(res) {
      res = res.data
      if (res.ret && res.data) {
        const data = res.data
        this.cities = data.cities
        this.hotCities = data.hotCities
      }
    }
  },
  components: {
    CityHeader,
    CitySearch,
    CityList,
    CityAlphabet
  }
}
</script>
<style lang="stylus" scoped>

</style>
