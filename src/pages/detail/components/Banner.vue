<template>
    <div>
        <div class="banner" @click="handleGallaryClick">
            <img class="banner-img" :src="bannerImg" />
            <div class="banner-info">
                <div class="banner-title">{{ this.sightName }}</div>
                <div class="banner-number"><span class="iconfont banner-icon">&#xe674;</span>{{ this.gallaryImgs.length }}</div>
            </div>
        </div>
        <fade-animation>
          <common-gallary :imgs="gallaryImgs" v-show="showGallary" @close="handleGallaryClose"></common-gallary>
        </fade-animation>
    </div>
</template>

<script>
import CommonGallary from 'common/gallary/Gallary'
import FadeAnimation from 'common/fade/Fade'
export default {
  name: 'DetailBanner',
  components: {
    CommonGallary,
    FadeAnimation
  },
  props: {
    sightName: String,
    bannerImg: String,
    gallaryImgs: Array
  },
  data () {
    return {
      showGallary: false
      // imgs: ['//img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_600x330_f922b488.jpg',
      //   'http://img1.qunarzz.com/sight/p0/1410/e3/73da8d3e19cdc41c1932d4fcd22ec792.water.jpg_r_800x800_7f96ccf9.jpg',
      //   'http://img1.qunarzz.com/wugc/p123/201211/19/a2045d091f02b25493835fbb.png_r_800x800_c59f0eba.png']
    }
  },
  methods: {
    handleGallaryClick () {
      this.showGallary = true
    },
    handleGallaryClose () {
      this.showGallary = false
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
            background-image: linear-gradient(top, rgba(0,0,0,0), rgba(0,0,0,0.8))
            .banner-title
                flex: 1
                font-size: .32rem
                padding: 0 .2rem
            .banner-number
                padding: 0 .4rem
                height: .32rem
                margin-top: .14rem
                line-height: .32rem
                border-radius: .2rem
                background: rgba(0,0,0,.8)
                font-size: .24rem
            .banner-icon
                font-size: .24rem
</style>
