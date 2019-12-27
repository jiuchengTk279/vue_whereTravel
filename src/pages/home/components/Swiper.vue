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
          imgUrl: 'https://h-des-activity-fecp.qunarzz.com/h_des_activity_fe_h_des_activity_fe/8c54576e74c6d4ea0062c9a664035262.jpg_750x200_9a39efd3.jpg'
        },
        {
          id: '0002',
          imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/201912/d6df0db510d7b9aaa3d9ce4cffafeca1.jpg_750x200_abb38f14.jpg'
        },
        {
          id: '0003',
          imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20197/0645bd625b46216a55e3835d0f677ce2.jpg_750x200_1e9a0cbf.jpg'
        },
        {
          id: '0004',
          imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/201911/4d9e45775ba63057e10f3c4d9d7b8cdd.jpg_750x200_345d57f5.jpg'
        },
        {
          id: '0005',
          imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20198/083c708a3949958bcbca0fcc0ea3d57f.jpg_750x200_e47acfc7.jpg'
        },
        {
          id: '0006',
          imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/201912/37c4edf7c033ada7b61a1f9d0acffd08.jpg_750x200_3223c943.jpg'
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
    padding-bottom: 27%
    background-color: #ccc
    .swiper-img
        width: 100%
</style>
