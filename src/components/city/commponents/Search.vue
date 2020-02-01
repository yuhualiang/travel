<template>
  <div>
      <div class="search">
        <input placeholder="输入城市名或拼音" type="text"
              v-model="keyword"
              class="search-input"
              @focus="showTag"
              @blur="showTag">
      </div>
      <div class="search-content" ref="search-content" v-show="keyword">
        <ul>
          <li v-for="item of list"
              :key="item.id"
              class="search-item border-bottom"
              @click="handleCityClick(item.name)">{{item.name}}</li>
          <li v-show="whetherList" class="search-item border-bottom">
            没有找到匹配数据
          </li>
        </ul>
      </div>
  </div>
</template>

<script>
import Bscroll from 'better-scroll'
import { mapMutations } from 'vuex'
export default {
  name: 'CitySearch',
  props: {
    cities: Object
  },
  data() {
    return {
      keyword: '',
      list: [],
      timer: null
    }
  },
  computed: {
    whetherList() {
      return !this.list.length
    }
  },
  watch: {
    keyword() {
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
            if (value.spell.indexOf(this.keyword) > -1 || value.name.indexOf(this.keyword) > -1) {
              result.push(value)
            }
          })
        }
        this.list = result
      }, 100)
    }
  },
  methods: {
    handleCityClick(city) {
      this.changeCity(city)
      this.$router.push('/')
    },
    ...mapMutations(['changeCity']),
    showTag() {
      this.$emit('showTag')
    }
  },
  mounted() {
    this.scroll = new Bscroll(this.$refs['search-content'])
  }
}
</script>
<style lang="stylus">
  @import '~styles/varibles.styl'
  .search
    height: .72rem
    padding: 0 .1rem
    background: $bgColor
    &-input
      box-sizing: border-box
      width: 100%
      height: .62rem
      padding: 0 .1rem
      line-height: .62rem
      text-align: center
      border-radius: .06rem
      color: #666666
  .search-content
    z-index: 1
    overflow: hidden
    position: absolute
    top: 1.58rem
    left: 0
    right: 0
    bottom: 0
    background: #eeeeee
    .search-item
      line-height: .62rem
      padding-left: .2rem
      color: #666666
      background: #ffffff
</style>
