<template>
    <div>
        <router-link tag="div" to="/" class="header-abs" v-show="showAbs">
            <div class="iconfont headerAbs-icon">&#xe606;</div>
        </router-link>
        <div class="header-fixed" v-show="!showAbs" :style="opacityStyle">
            <router-link to="/">
                <div class="iconfont header-fixed-back">&#xe606;</div>
            </router-link>
            景点详情
        </div>
    </div>
</template>

<script>
export default {
  name: 'DetailHeader',
  data () {
    return {
      showAbs: true,
      opacityStyle: {
        opacity: 0
      }
    }
  },
  //   使用了keep-alive缓存动态组件，只要切换展示页面就会触发activated()钩子函数，然后就会判断显示隐藏
  activated () {
    window.addEventListener('scroll', this.hanleScroll)
  },
  // 全局事件的解绑
  deactivated () {
    window.removeEventListener('scroll', this.hanleScroll)
  },
  methods: {
    hanleScroll () {
      const top = document.documentElement.scrollTop
      if (top > 60) {
        let opacity = top / 140
        opacity = opacity > 1 ? 1 : opacity
        this.opacityStyle = { opacity }
        this.showAbs = false
      } else {
        this.showAbs = true
      }
    }
  }
}
</script>

<style lang="stylus" scoped>
    @import '~styles/varibles.styl'
    .header-abs
        position: absolute
        left: .2rem
        top: .2rem
        width: .8rem
        height: .8rem
        line-height: .8rem
        border-radius: .4rem
        text-align: center
        background: rgba(0, 0, 0, .8)
        .headerAbs-icon
            color: #fff
            font-size: .4rem
    .header-fixed
        z-index: 2
        position: fixed
        top: 0
        left: 0
        right: 0
        height: .86rem
        line-height: .86rem
        overflow: hidden
        text-align: center
        color: #fff
        background: $bgColor
        font-size: .32rem
        .header-fixed-back
            position: absolute
            top: 0
            left: 0
            width: .64rem
            text-align: center
            font-size: .4rem
            color: #fff
</style>
