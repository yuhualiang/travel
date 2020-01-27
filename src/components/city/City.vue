<template>
  <div>
    <city-header></city-header>
    <city-search></city-search>
    <city-list></city-list>
  </div>
</template>

<script>
import CityHeader from './commponents/Header'
import CitySearch from './commponents/Search'
import CityList from './commponents/List'

export default {
  name: 'City',
  components: {
    CityHeader,
    CitySearch,
    CityList
  }
}
</script>
<style lang="stylus" scoped>

</style>
