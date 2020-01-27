<template>
  <div>
    <city-header></city-header>
    <city-search></city-search>
    <city-list :cities="cities" :hot="hotCities"></city-list>
    <city-alphabet :cities="cities"></city-alphabet>
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
      hotCities: []
    }
  },
  mounted() {
    this._getCityInfo()
  },
  methods: {
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
        console.log(res.data.hotCities)
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
