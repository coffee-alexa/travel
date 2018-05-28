<template>
<div>
    <div class="title">热销推荐</div>
    <ul>
        <li class="item"
        v-for='item of recommendList'
        :key="item.id">
                <img class="item-img" :src="item.srcUrl" alt="">
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
  name: 'HomeCommend',
  data () {
    return {
      recommendList: [{
        id: '0001',
        title: '长春必游TOP5',
        desc: '这是一片历史与现实交映的黑土地',
        button: '查看详情',
        srcUrl: 'http://img1.qunarzz.com/sight/p0/1507/f0/45ad118808cbfbdd1ca292f6939bdda5.water.jpg_150x150_1166f15a.jpg'
      },
      {
        id: '0002',
        title: '长春必游TOP5',
        desc: '这是一片历史与现实交映的黑土地',
        button: '查看详情',
        srcUrl: 'http://img1.qunarzz.com/sight/p0/1507/f0/45ad118808cbfbdd1ca292f6939bdda5.water.jpg_150x150_1166f15a.jpg'

      },
      {
        id: '0003',
        title: '长春必游TOP5',
        desc: '这是一片历史与现实交映的黑土地',
        button: '查看详情',
        srcUrl: 'http://img1.qunarzz.com/sight/p0/1507/f0/45ad118808cbfbdd1ca292f6939bdda5.water.jpg_150x150_1166f15a.jpg'

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
    .item {
        overflow: hidden
        display: flex
        height: 1.9rem
        .item-img {
            width: 1.7rem
            height: 1.7rem
            padding: .1rem
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
    }
</style>
