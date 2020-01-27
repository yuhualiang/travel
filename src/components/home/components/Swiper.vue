<template>
  <div class="wrapper">
    <swiper :options="swiperOption" v-if="swiperList.length">
      <swiper-slide v-for="(item, index) in swiperList" :key="index">
        <img class="swiper-img" :src="item" />
      </swiper-slide>
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  props: {
    swiperList: Array
  },
  data() {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true,
        autoplay: 2500
      }
    }
  }
}
</script>

<style lang="stylus" scoped>
.wrapper >>> .swiper-pagination-bullet-active
  background-color: #ffffff
.wrapper
  overflow: hidden
  width: 100%
  height: 0
  padding-bottom: 26.66%
  background-color: #eee
  .swiper-img
    width: 100%
</style>
