<template>
  <div class="swiper">
    <swiper :options="swiperOption" v-if="swiperList.length">
        <swiper-slide v-for="item of swiperList" :key="item.id">
            <img class="swiper-img" :src="item.imgUrl" >
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
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      }
    }
  }
}
</script>

<style lang="stylus" scoped>
.swiper >>>.swiper-pagination-bullet-active {
    background: #fff
}
.swiper {
    overflow hidden
    width: 100%
    height: 0px
    padding-bottom: 26.67%
    .swiper-img {
    width: 100%
    }
}
</style>
