<template>
    <div>
        <router-link
            tag="div"
            to="/"
            class="header-abs"
            v-show="showAbs">
            <span class="iconfont header-back-icon">&#xe624;</span>
        </router-link>
        <div
            class="header-fixed"
            v-show="!showAbs"
            :style="opacityStyle">
            <router-link to="/">
            <span class="iconfont header-back">&#xe624;</span>
            </router-link>
            景点详情
        </div>
    </div>
</template>

<script>
export default {
  name: 'Header',
  data () {
    return {
      showAbs: true,
      opacityStyle: {
        opacity: 0
      }
    }
  },
  methods: {
    handleScroll () {
      const top = document.documentElement.scrollTop
      console.log(top)
      if (top > 60) {
        let opacity = top / 140
        opacity = opacity > 1 ? 1 : opacity
        this.opacityStyle = { opacity: opacity }
        this.showAbs = false
      } else {
        this.showAbs = true
      }
    }
  },
  activated () {
    window.addEventListener('scroll', this.handleScroll)
  },
  deactivated () {
    window.removeEventListener('scroll', this.handleScroll)
  }
}
</script>

<style lang="stylus" scoped>
@import '~@/assets/styles/varibles.styl'
    .header-abs
        position: absolute
        top: .2rem
        left: .2rem
        width: .66rem
        height: .66rem
        line-height: .66rem
        border-radius: .33rem
        text-align: center
        background: rgba(0, 0, 0, .6)
        .header-back-icon
            color: #fff
            font-size: .33rem
    .header-fixed
        z-index: 2
        position: fixed
        top: 0
        left: 0
        right:0
        height: $headerHeaght
        line-height: .86rem
        text-align: center
        color: #fff
        background: $bgColor
        font-size: .32rem
        .header-back
            position: absolute
            top: 0
            left: 0
            width: .64rem
            text-align: center
            color: #fff
            font-size: $fontSize
</style>
