<template>
  <a class="recommend-list">
    <img :src="item.image_url" alt="" width="100%">
     <h4 class="item-title" v-text="item.goods_name"></h4>
    <div class="item-bottom">
       <span class="item-price">￥{{item.normal_price/100}}</span>
       <span class="item-sales">{{item.sales_tip}}</span>
       <button class="item-btn" @click.prevent="clickCellBtn(item.goods_id)">发现 ></button>
    </div>
  </a>
</template>

<script>
    export default {
        name: "ShopList",
        props:{
          item:Object,
          clickCellBtn:{
             type:Function,
             default:()=>{}
          }
        }
    }
</script>

<style scoped lang="stylus" rel="stylesheet/stylus">
  .recommend-list:nth-child(2n-1)
    margin-right 1%
  .recommend-list
    background-color #FFF
    width 49.5%
    padding-bottom 1.5rem
    margin-bottom 1.5rem
    .item-title
      line-height 2rem
      font-size 1.3rem
      font-weight lighter
      height 2rem
      overflow hidden
      margin 0.5rem 0
      padding 0 0.5rem
    .item-bottom
      display flex
      flex-direction row
      align-items center
      padding 0 0.6rem
      .item-price
        flex 2
        color red
        font-weight bolder
        font-size 1.2rem
      .item-sales
        flex 3
        font-size 1rem
        color #666666
      .item-btn
        flex 3
        border 0.1rem solid orangered
        height 2.6rem
        border-radius 0.5rem
        font-size 1rem
        background-color transparent
        color red
        line-height  2.6rem
</style>
