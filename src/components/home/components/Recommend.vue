<template>
  <div>
    <div class="title">热销推荐</div>
    <ul>
      <li class="item border-bottom" v-for="item in hotList" :key="item.id">
        <img class="item-img" :src="item.imgUrl" />
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.price}}</p>
          <button class="item-button">查看详情</button>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'Recommend',
  data() {
    return {
      'hotList': [
        {
          'title': '大连森林动物园',
          'price': '￥58',
          'imgUrl': 'http://img1.qunarzz.com/sight/p0/1707/57/5729585581b6732fa3.water.jpg_150x150_88ed4437.jpg'
        },
        {
          'title': '大连圣亚海洋世界',
          'price': '￥25',
          'imgUrl': 'http://img1.qunarzz.com/sight/p0/201404/23/04b92c99462687fa1ba45c1b5ba4ad77.jpg_150x150_2c4b6f2f.jpg'
        },
        {
          'title': '老虎滩海洋公园',
          'price': '￥50',
          'imgUrl': 'http://img1.qunarzz.com/sight/p0/1602/39/39f6b1003abe1b2790.img.jpg_150x150_a9877501.jpg'
        },
        {
          'title': '旅顺203樱花园',
          'price': '￥218',
          'imgUrl': 'http://img1.qunarzz.com/sight/p0/1804/a2/a2a3dd4f0bf42f4da3.img.jpg_150x150_e9128a33.jpg'
        },
        {
          'title': '海昌发现王国',
          'price': '￥60',
          'imgUrl': 'http://img1.qunarzz.com/sight/p0/1703/94/944fc059260bd728a3.water.jpg_150x150_f3152ca6.jpg'
        },
        {
          'title': '大连森林动物园',
          'price': '￥58',
          'imgUrl': 'http://img1.qunarzz.com/sight/p0/1707/57/5729585581b6732fa3.water.jpg_150x150_88ed4437.jpg'
        },
        {
          'title': '大连圣亚海洋世界',
          'price': '￥25',
          'imgUrl': 'http://img1.qunarzz.com/sight/p0/201404/23/04b92c99462687fa1ba45c1b5ba4ad77.jpg_150x150_2c4b6f2f.jpg'
        },
        {
          'title': '老虎滩海洋公园',
          'price': '￥50',
          'imgUrl': 'http://img1.qunarzz.com/sight/p0/1602/39/39f6b1003abe1b2790.img.jpg_150x150_a9877501.jpg'
        },
        {
          'title': '旅顺203樱花园',
          'price': '￥218',
          'imgUrl': 'http://img1.qunarzz.com/sight/p0/1804/a2/a2a3dd4f0bf42f4da3.img.jpg_150x150_e9128a33.jpg'
        },
        {
          'title': '海昌发现王国',
          'price': '￥60',
          'imgUrl': 'http://img1.qunarzz.com/sight/p0/1703/94/944fc059260bd728a3.water.jpg_150x150_f3152ca6.jpg'
        }
      ]
    }
  }
}
</script>

<style lang="stylus" scoped>
 @import '~styles/mixins.styl'
.title
  margin-top: .2rem
  line-height: .8rem
  background: #eee
  text-indent: .2rem
.item
  overflow: hidden
  display: flex
  height: 1.9rem
  &-img
    height: 1.7rem
    width: 1.7rem
    padding: .1rem
  &-info
    flex: 1
    padding: .1rem
    min-width: 0
    .item-title
      line-height: .54rem
      font-size: .32rem
      ellipis()
    .item-desc
      line-height: .4rem
      color: #ccc
      ellipis()
    .item-button
      line-height: .44rem
      margin-top: .16rem
      background: #ff9300
      padding: 0 .2rem
      border-radius: .06rem
      color: #fff
</style>
