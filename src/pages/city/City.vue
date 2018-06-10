<template>
    <div>
        <city-header></city-header>
        <city-search
            :cities='cities'></city-search>
        <city-list
            :hotCities='hotCities'
            :cities='cities'
            :letter='letter'></city-list>
        <city-alphabet
            :cities='cities'
            @change='handleLetterChange'></city-alphabet>
    </div>
</template>

<script>
import citySearch from './components/Search'
import cityHeader from './components/Header'
import cityList from './components/List'
import cityAlphabet from './components/Alphabet'
import axios from 'axios'

export default {
  name: 'City',
  components: {
    citySearch: citySearch,
    cityHeader: cityHeader,
    cityList: cityList,
    cityAlphabet: cityAlphabet
  },
  data () {
    return {
      hotCities: [],
      cities: {},
      letter: ''
    }
  },
  methods: {
    getCityInfo () {
      axios.get('/api/city.json')
        .then(this.getCityInfoSuc)
    },
    getCityInfoSuc (res) {
      res = res.data
      if (res.ret && res.data) {
        var data = res.data
        this.hotCities = data.hotCities
        this.cities = data.cities
      }
    },
    handleLetterChange (letter) {
      this.letter = letter
    }
  },
  mounted () {
    this.getCityInfo()
  }
}
</script>

<style lang="stylus" scoped>

</style>
