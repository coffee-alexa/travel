<template>
    <div class="icons" v-if="pages.length">
        <swiper :options="swiperOption">
            <swiper-slide v-for="(page, index) of pages" :key="index">
                <div
                    class="icon"
                    v-for="item of page"
                    :key="item.id"
                >
                    <div class=icon-img>
                        <img class="icon-img-concent" :src="item.imgUrl">
                    </div>
                    <p class="icon-desc">{{item.desc}}</p>
                </div>
            </swiper-slide>
        </swiper>
    </div>
</template>

<script>
export default {
  name: 'HomeIcons',
  props: {
    iconList: Array
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
      this.iconList.forEach((item, index) => {
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
  @import '~@/assets/styles/varibles.styl'

    .icons {
        overflow: hidden
        width: 100%
        height: 0px
        padding-bottom: 50%
        margin-top: .2rem
        .icon {
            overflow: hidden
            float: left
            position: relative
            width: 25%
            height: 0px
            padding-bottom: 25%
            .icon-img {
                position: absolute
                top: 0
                left: 0
                right: 0
                bottom: .44rem
                box-sizing: border-box
                padding: .1rem
                .icon-img-concent {
                    display: block
                    margin: 0 auto
                    height: 100%
                }
            }
            .icon-desc {
                position: absolute
                left: 0
                right: 0
                bottom: 0
                height: .44rem
                line-height: .44rem
                text-align: center
                color: $darkTextColor
                ellipsis()
            }
        }
    }
</style>
