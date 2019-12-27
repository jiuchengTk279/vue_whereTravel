<template>
    <div class="wrapper">
        <swiper :options="swiperOption">
            <!-- slides -->
            <swiper-slide v-for="item of swiperList" :key="item.id">
                <img  class="swiper-img" :src="item.imgUrl" />
            </swiper-slide>
            <!-- Optional controls -->
            <div class="swiper-pagination"  slot="pagination"></div>
            <!-- <div class="swiper-button-prev" slot="button-prev"></div>
            <div class="swiper-button-next" slot="button-next"></div>
            <div class="swiper-scrollbar"   slot="scrollbar"></div> -->
        </swiper>
    </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      },
      swiperList: [
        {
          id: '0001',
          imgUrl: 'https://imgs.qunarzz.com/vc/bc/9e/bf/9692c9ac6e2ca1ba56d41ea6f0.jpg_92.jpg'
        },
        {
          id: '0002',
          imgUrl: 'https://img1.qunarzz.com/vc/cf/64/4c/ec5cf27cd2da692b3e1c240bd8.jpg_640x348x92.jpg'
        },
        {
          id: '0003',
          imgUrl: 'https://imgs.qunarzz.com/vc/9e/9c/aa/17bc083737b8c0bc2ace59872c.jpg_92.jpg'
        },
        {
          id: '0004',
          imgUrl: 'https://img1.qunarzz.com/vc/54/21/86/b52e83239fb2c9ba12f4557b74.jpg_650x360x92.jpg'
        }]
    }
  }
}
</script>

<style lang="stylus" scoped>
  .wrapper >>> .swiper-pagination-bullet-active
    background: #fff
  .wrapper
    touch-action: none
    overflow: hidden
    width: 100%
    height: 0
    padding-bottom: 45%
    background-color: #ccc
    .swiper-img
        width: 100%
</style>
