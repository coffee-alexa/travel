<template>
    <div class="list" ref="wrapper">
        <div>
            <div class="area">
                <div class="title border-topbottom">当前城市</div>
                <div class="button-list">
                    <div class="button-wrapper">
                    <div class="button">{{this.city}}</div>
                    </div>
                </div>
            </div>
            <div class="area">
                <div class="title border-topbottom">热门城市</div>
                <div class="button-list">
                    <div
                        class="button-wrapper"
                        v-for="item in hotCities"
                        :key="item.id"
                        @click="handleCityClick(item.name)"
                        >
                    <div class="button">{{item.name}}</div>
                    </div>
                </div>
            </div>
            <div
                class="area"
                v-for="(items, key) of cities"
                :key="items.id"
                :ref="key"
                >
                <div class="title border-topbottom">{{key}}</div>
                <div
                    class="item-list"
                    v-for="item of items"
                    :key="item.id"
                    @click="handleCityClick(item.name)">
                    <div class="item border-bottom">{{item.name}}</div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import BScroll from 'better-scroll'
import { mapState, mapMutations } from 'vuex'
export default {
  name: 'cityList',
  mounted () {
    this.scroll = new BScroll(this.$refs.wrapper)
  },
  props: {
    hotCities: Array,
    cities: Object,
    letter: String
  },
  computed: {
    ...mapState(['city'])
  },
  methods: {
    handleCityClick (city) {
      this.changeCity(city)
      this.$router.push('/')
    },
    ...mapMutations(['changeCity'])
  },
  watch: {
    letter () {
      if (this.letter) {
        const element = this.$refs[this.letter][0]
        this.scroll.scrollToElement(element)
      }
    }
  }
}
</script>

<style lang="stylus" scoped>
    @import '~@/assets/styles/varibles.styl'
    .border-topbottom
        &:before
            border-color: #ccc
        &:after
            border-color: #ccc
    .border-bottom
        &:before
            border-color: #ccc
    .list
        position: absolute
        overflow: hidden
        top: 1.56rem
        left: 0
        right: 0
        bottom: 0
        .title
            line-height: .44rem
            background: #eee
            padding-left: .2rem
            color: #666
            font-size: .26rem
        .button-list
            overflow: hidden
            padding: .1rem
            width: 92.6%
            .button-wrapper
                float: left
                width: 33.33%
                .button
                    margin: .1rem
                    padding: .1rem 0
                    text-align: center
                    border: .02rem solid #ccc
                    border-radius: .1rem
        .item-list
            .item
                line-height: .68rem
                padding-left: .2rem
</style>
