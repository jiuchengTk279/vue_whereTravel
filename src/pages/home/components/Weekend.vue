<template>
    <div>
        <div class="title">周末去哪儿</div>
        <ul>
            <li class="item border-bottom" v-for="item of weekendList" :key="item.id">
                <div class="item-img-wrapper">
                    <img class="item-img" :src="item.imgUrl" />
                </div>
                <div class="item-info">
                    <p class="item-title">{{ item.title }}</p>
                    <p class="item-desc">{{ item.desc }}<span>{{ item.price }}</span></p>
                </div>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
  name: 'HomeWeekend',
  data () {
    return {
      weekendList: [
        {
          id: '0001',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1607/7c/7cda8b6782dabd80b4.img.jpg_200x200_2039e660.jpg',
          title: '上海迪士尼乐园',
          desc: '全球最大的迪士尼城堡',
          price: '￥399元起'
        },
        {
          id: '0002',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1912/e3/e34a3084c05532cca3.img.jpg_200x200_ecbe41c5.jpg',
          title: '上海野生动物园',
          desc: '会跳芭蕾的小海狮们~',
          price: '￥115元起'
        },
        {
          id: '0003',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1906/19/19b7939928a0200da3.img.jpg_200x200_6879c7f7.jpg',
          title: '上海海昌海洋公园',
          desc: '海洋生物',
          price: '￥139元起'
        },
        {
          id: '0004',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1811/e4/e4b9b471d2afc473a3.img.jpg_200x200_9a7794fc.jpg',
          title: '上海欢乐谷',
          desc: '敢上1200米长的木质过山车吗？',
          price: '￥219元起'
        },
        {
          id: '0005',
          imgUrl: 'http://img1.qunarzz.com/tuan/team2/1507/2c/83e0e0e7ae082a.jpg_200x200_6d7378b2.jpg',
          title: '东方明珠',
          desc: '259米透明悬空观光廊了解一下~',
          price: '￥80元起'
        },
        {
          id: '0006',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1612/34/349ee417b69fed40a3.img.jpg_200x200_9c5356e9.jpg',
          title: '上海星空错觉艺术馆',
          desc: '你就是故事的主角',
          price: '￥66元起'
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
        background-color: #eee
        text-indent: .2rem
    .item-img-wrapper
        overflow: hidden
        height: 0
        padding-bottom: 33.9%
        .item-img
            width: 100%
    .item-title
        line-height: .54rem
        font-size: .32rem
        ellipsis()
    .item-desc
        line-height: .4rem
        color: #ccc
        ellipsis()
        span
            margin-left: 0.3rem
            color: #FF5555
</style>
