<template>
    <div class="icons">
        <swiper :options="swiperOption">
            <swiper-slide v-for="(page,index) of pages" :key="index">
                <div class="icon" v-for="item of page" :key="item.id">
                    <div class="icon-img">
                            <img class="icon-img-content" :src="item.imgUrl">
                    </div>
                    <p class="icon-desc">{{ item.desc }}</p>
                </div>
            </swiper-slide>
        </swiper>
    </div>
</template>

<script>
export default {
  name: 'HomeIcons',
  // data () {
  //   return {
  //     iconList: [
  //       {
  //         id: '0001',
  //         img: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
  //         desc: '景点门票'
  //       },
  //       {
  //         id: '0002',
  //         img: 'http://img1.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png',
  //         desc: '一日游'
  //       },
  //       {
  //         id: '0003',
  //         img: 'http://img1.qunarzz.com/piao/fusion/1803/de/f26be47a6bf02a02.png',
  //         desc: '上海迪士尼'
  //       },
  //       {
  //         id: '0004',
  //         img: 'https://img1.qunarzz.com/piao/fusion/1810/50/26ffa31b56646402.png',
  //         desc: '上海海昌'
  //       },
  //       {
  //         id: '0005',
  //         img: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/201912/9480e99a101564a22dfff0c4b9d0861c.png',
  //         desc: '上海杜莎'
  //       },
  //       {
  //         id: '0006',
  //         img: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20194/3ef092d0a89ffddb7f781cda30c8ae49.png',
  //         desc: '错峰出游'
  //       },
  //       {
  //         id: '0007',
  //         img: 'http://img1.qunarzz.com/piao/fusion/1803/ab/6f7d6e44963c9302.png',
  //         desc: '温泉滑雪'
  //       },
  //       {
  //         id: '0008',
  //         img: 'http://img1.qunarzz.com/piao/fusion/1803/3e/86314b2af03b7502.png',
  //         desc: '黄浦江游船'
  //       },
  //       {
  //         id: '0009',
  //         img: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/201912/9480e99a101564a22dfff0c4b9d0861c.png',
  //         desc: '上海杜莎'
  //       },
  //       {
  //         id: '0010',
  //         img: 'http://img1.qunarzz.com/piao/fusion/1803/47/c2b659e048b11602.png',
  //         desc: '上海野生动物园'
  //       }
  //     ]
  //   }
  // },
  props: {
    list: Array
  },
  data () {
    return {
      swiperOption: {
        autoplay: false
      }
    }
  },
  computed: {
    pages () {
      const pages = []
      this.list.forEach((item, index) => {
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
        .icon
            position: relative
            overflow: hidden
            float: left
            width: 25%
            height: 0
            padding-bottom: 25%
            .icon-img
                position: absolute
                top: 0
                left: 0
                right: 0
                bottom: .44rem
                box-sizing: border-box
                padding: .1rem
                .icon-img-content
                    display: block
                    margin: 0 auto
                    height: 100%
            .icon-desc
                position: absolute
                left: 0
                right: 0
                bottom: 0
                height: .44rem
                line-height: .44rem
                color: $darkTextColor
                text-align: center
                ellipsis()
</style>
