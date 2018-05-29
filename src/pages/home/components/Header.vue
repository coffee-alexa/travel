<template lang="html">
  <div class="header">
    <div class="header-left">
        <span class="iconfont back-icon">&#xe624;</span>
    </div>
    <div class="header-input">
      <span class="iconfont">&#xe632;</span>
      请输入
    </div>
    <div class="header-right">
      {{this.city}}
      <span class="iconfont arrow-icon">&#xe64a;</span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomeHeader',
  swiperOption: {
    pagination: '.swiper-pagination',
    loop: true
  },
  props: {
    city: String
  }
}
</script>

<style lang="stylus" scoped>
  @import '~@/assets/styles/varibles.styl'
  .header {
    display: flex
    line-height: .86rem
    background: $bgColor
    color: #fff
    .header-left {
      width: .64rem
      float: left
      text-align: center
      .back-icon {
        text-align: center
        font-size: .4rem
      }
    }
    .header-input {
      flex: 1
      height: .64rem
      line-height: .64rem
      margin-top: .12rem
      margin-left: .2rem
      padding-left: .2rem
      background: #fff
      border-radius: .1rem
      color: #ccc
    }
    .header-right {
      width: 1.12rem
      float: right
      text-align: center
      .arrow-icon {
        margin-left: -.04rem
        font-size: 0.24rem
      }
    }
  }
</style>
