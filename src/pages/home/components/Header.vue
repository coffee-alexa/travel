<template lang="html">
  <div class="header">
    <div class="header-left">left</div>
    <div class="header-input">
      input
    </div>
    <div class="header-right">right</div>
  </div>
</template>

<script>
export default {
  name: 'HomeHeader'
}
</script>

<style lang="stylus" scoped>
  .header {
    display: flex
    line-height: .86rem
    background: #00bcd4
    color: #fff
  }
  .header-left {
    width: .64rem
    float: left
  }
  .header-input {
    flex: 1
    height: .64rem
    line-height: .64rem
    margin-top: .12rem
    margin-left: .2rem
    background: #fff
    border-radius: .1rem
  }
  .header-right {
    width: 1.12rem
    float: right
    text-align: center
  }
</style>
