<template>
<div>
    <div class="title">周末去哪儿</div>
    <ul>
        <li class="item"
        v-for='item of recommendList'
        :key="item.id">
            <div class="item-img-wrapper">
                <img class="item-img" :src="item.srcUrl" alt="">
            </div>
            <div class="item-info">
                <p class="item-title">{{item.title}}</p>
                <p class="item-desc">{{item.desc}}</p>
                <button class="item-button">{{item.button}}</button>
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
      recommendList: [{
        id: '0001',
        title: '长春必游TOP5',
        desc: '这是一片历史与现实交映的黑土地',
        button: '查看详情',
        srcUrl: 'http://img1.qunarzz.com/sight/source/1505/c2/0be94f64d9df91.jpg_r_640x214_130f7614.jpg'
      },
      {
        id: '0002',
        title: '长春必游TOP5',
        desc: '这是一片历史与现实交映的黑土地',
        button: '查看详情',
        srcUrl: 'http://img1.qunarzz.com/sight/source/1505/c2/0be94f64d9df91.jpg_r_640x214_130f7614.jpg'
      },
      {
        id: '0003',
        title: '长春必游TOP5',
        desc: '这是一片历史与现实交映的黑土地',
        button: '查看详情',
        srcUrl: 'http://img1.qunarzz.com/sight/source/1505/c2/0be94f64d9df91.jpg_r_640x214_130f7614.jpg'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
@import '~@/assets/styles/minins.styl'
    .title {
        margin-top: .2rem
        line-height: .8rem
        background: #eee
        text-indent: .2rem
    }
    .item-img-wrapper {
        overflow: hidden
        height: 0px
        padding-bottom: 33.7%
    }
    .item-img {
        width: 100%
    }
    .item-info {
        flex: 1
        padding: .1rem
        .item-title {
            line-height: .54rem
            font-size: .32rem
            ellipsis()
        }
        .item-desc {
            line-height: .4rem
            color: #ccc
            ellipsis()
        }
        .item-button {
            line-height: .44rem
            margin-top: .16rem
            background: #ff9300
            padding: 0 .2rem
            border-radius: .06rem
            color: #fff
        }
    }

</style>
