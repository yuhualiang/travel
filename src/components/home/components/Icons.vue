<template>
    <div class="icons">
      <swiper :options="swiperOption">
        <swiper-slide v-for="(page, ke) in pages" :key="ke">
          <div class="icon" v-for="item in page" :key="item.id">
            <div class="icon-img">
              <img class="icon-img-content" :src="item.imgUrl" />
            </div>
            <p class="icon-desc">{{item.title}}</p>
          </div>
        </swiper-slide>
      </swiper>

    </div>
</template>

<script>
export default {
  name: 'Icons',
  data() {
    return {
      swiperOption: {
        autoplay: false
      },
      'iconList': [
        {
          'id': '0001',
          'title': '景点门票',
          'imgUrl': 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png'
        },
        {
          'id': '0002',
          'title': '一日游',
          'imgUrl': 'http://img1.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png'
        },
        {
          'id': '0003',
          'title': '本地玩乐',
          'imgUrl': 'http://img1.qunarzz.com/piao/fusion/1803/f5/a963333e1fa802.png'
        },
        {
          'id': '0004',
          'title': '动植物园',
          'imgUrl': 'http://img1.qunarzz.com/piao/fusion/1803/76/eb88861d78fb9902.png'
        },
        {
          'id': '0005',
          'title': '必游榜单',
          'imgUrl': 'http://img1.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png'
        },
        {
          'id': '0006',
          'title': '自然风光',
          'imgUrl': 'http://img1.qunarzz.com/piao/fusion/1803/96/c70f1e85ae4a4f02.png'
        },
        {
          'id': '0007',
          'title': '海滨海岛',
          'imgUrl': 'http://img1.qunarzz.com/piao/fusion/1803/27/dac2bcf9added702.png'
        },
        {
          'id': '0008',
          'title': '踏青赏花',
          'imgUrl': 'http://img1.qunarzz.com/piao/fusion/1803/bd/9f7b9b2b60c1502.png'
        },
        {
          'id': '0009',
          'title': '城市观光',
          'imgUrl': 'http://img1.qunarzz.com/piao/fusion/1803/b6/37560ece9c62b502.png'
        },
        {
          'id': '0010',
          'title': '全部玩乐',
          'imgUrl': 'http://img1.qunarzz.com/piao/fusion/1803/80/416c6ab3368d1f02.png'
        }
      ]
    }
  },
  computed: {
    pages() {
      const pages = []
      this.iconList.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>

<style lang="stylus" scoped>
 @import '~styles/varibles.styl'
 @import '~styles/mixins.styl'
  .icons >>> .swiper-container
    height: 0
    padding-bottom: 50%
  .icons
    margin-top: .2rem
  .icons
    width: 100%
    height: 0
    padding-bottom: 50%
    .icon
      float: left
      width: 25%
      height: 0
      padding-bottom: 25%
      position: relative
      &-img
        position: absolute
        top: 0
        left: 0
        right: 0
        bottom: .44rem
        box-sizing: border-box
        padding: .1rem
        &-content
          display: block
          margin: 0 auto
          height: 100%
      &-desc
        position: absolute
        left: 0
        right: 0
        bottom: 0
        height: .44rem
        line-height: .44rem
        color: $darkTextColor
        text-align: center
        ellipis()
</style>
