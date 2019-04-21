<template>
<div>

     <div class="banner" @click="handleGallaryClick">
  <img class="banner-img" src="//img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_600x330_f922b488.jpg" alt="">
  <div class="banner-info">
      <div class="banner-tittle">好风景好风景真的好看的啊</div>
      <div class="banner-number"><span class="iconfont">&#xe6dd;</span>39</div>
  </div>
  </div>
  <common-gallery :imgs="imgs" v-show="showGallery"></common-gallery>
</div>
 
</template>

<script>
import CommonGallery from 'common/gallary/Gallary'
export default {
  name: 'Banner',
  components:{
      CommonGallery
  },
  data () {
    return {
        showGallery:false,
     imgs:['//img1.qunarzz.com/sight/p0/1803/b4/b4a14ee953d8f395a3.img.jpg_r_800x800_3d772856.jpg',
     '//img1.qunarzz.com/sight/p0/1803/ca/ca99dc8105918228a3.img.jpg_r_800x800_ad94578a.jpg']
    }
  },
  methods:{
      handleGallaryClick () {
          this.showGallery=true
      }
  }
}
</script>

<style lang="stylus" scoped>
 .banner
    position: relative
    overflow: hidden
    height: 0
    padding-bottom: 55%
    .banner-img
      width: 100%
    .banner-info
      display: flex
      position: absolute
      left: 0
      right: 0
      bottom: 0
      line-height: .6rem
      color: #fff
      background-image: linear-gradient(top, rgba(0, 0, 0, 0), rgba(0, 0, 0, 0.8))
      .banner-tittle
        flex: 1
        font-size: .32rem
        padding: 0 .2rem
      .banner-number
        height: .32rem
        line-height: .32rem
        margin-top: .14rem
        padding: 0 .4rem
        border-radius: .2rem
        background: rgba(0, 0, 0, .8)
        font-size: .24rem
        .banner-icon
          font-size: .24rem
</style>
