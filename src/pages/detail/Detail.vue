<template>
    <div>
        <Banner
            :sightName='sightName'
            :bannerImg="bannerImg"
            :gallaryImgs="gallaryImgs"></Banner>
        <Header></Header>
        <div class="content"></div>
    </div>
</template>

<script>
import Banner from './components/Banner'
import Header from './components/Header'
import axios from 'axios'

export default {
  name: 'Detail',
  data () {
    return {
      sightName: '',
      bannerImg: '',
      gallaryImgs: []
    }
  },
  components: {
    Banner: Banner,
    Header: Header
  },
  methods: {
    getDetailInfo () {
      axios.get('/api/detail.json', {
        params: {
          id: this.$route.params.id
        }
      }).then(this.getDetailInfoSuc)
    },
    getDetailInfoSuc (res) {
      res = res.data
      if (res.ret && res.data) {
        var data = res.data
        this.sightName = data.sightName
        this.bannerImg = data.bannerImg
        this.gallaryImgs = data.gallaryImgs
      }
    }
  },
  mounted () {
    this.getDetailInfo()
  }
}
</script>

<style lang="stylus" scoped>
    .content
        height: 50rem
</style>
