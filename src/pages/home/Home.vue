<template>
  <home-header></home-header>
</template>

<script>
import HomeHeader from './components/Header'
export default {
  name: 'Home',
  components: {
    HomeHeader: HomeHeader
  }
}
</script>

<style lang="css">
  .link {
    font-size: 18px;
  }
</style>
