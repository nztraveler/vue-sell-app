<template>
  <div class="header">
    <div class="content-wrapper">
      <div class="avatar">
        <img width="64" height="64" :src="seller.avatar" alt="头像">
      </div>
      <div class="seller-content">
        <div class="title">
          <span class="brand"></span>
          <span class="seller-name">{{seller.name}}</span>
        </div>
        <p class="delivery">{{seller.description}}/{{seller.deliveryTime}}分钟送达</p>
        <div v-if="seller.supports" class="supports">
          <span class="supports-icon" :class="classMap[seller.supports[0].type]"></span>
          <span class="supports-text">{{seller.supports[0].description}}</span>
        </div>
      </div>
      <div v-if="seller.supports" class="support-more-btn">
        <span class="support-num">{{seller.supports.length}}个</span>
        <i class="icon-keyboard_arrow_right"></i>
      </div>
    </div>
    <div class="bulletin-wrapper">
      <span class="bulletin-icon"></span><span class="bulletin-preview">{{seller.bulletin}}</span>
      <i class="icon-keyboard_arrow_right"></i>
    </div>
    <div class="header-bg">
      <img width="100%" height="100%" :src="seller.avatar">
    </div>
  </div>
</template>

<script>
  export default {
    name: 'v-header',
    data () {
      return {
        classMap: ['decrease', 'discount', 'special', 'invoice', 'guarantee']
      }
    },
    props: {
      seller: {
        type: Object
      }
    },
    created () {
      // this.classMap = ['decrease', 'discount', 'special', 'invoice', 'guarantee']
    }
  }
</script>

<style lang="stylus" rel="stylesheet/stylus">
  @import "../../common/stylus/mixin.styl"
  .header
    position relative
    color #fff
    overflow hidden
    background-color rgba(7, 17, 27, .5)
    .content-wrapper
      position relative
      padding 24px 12px 18px 24px
      font-size 0
      .avatar
        display inline-block
        vertical-align top
        img
          border-radius 2px
      .seller-content
        display inline-block
        padding-left 16px
        .title
          padding-top 2px
          font-size 0
          .brand
            display inline-block
            vertical-align top
            width 30px
            height 18px
            bg-img('brand')
            background-size 30px 18px
          .seller-name
            padding-left 6px
            line-height 18px
            font-size 16px
            font-weight bold
        .delivery
          margin-top 8px
          line-height 12px
          font-size 12px
        /*font-weight 200*/
        .supports
          /*display: -webkit-box;*/
          /*display: box;*/
          /*display: -webkit-flex;*/
          /*display: flex;*/
          /*-webkit-box-align: center;*/
          /*box-align: center;*/
          /*-webkit-align-items: center;*/
          /*align-items: center;*/
          /*display table*/
          margin 10px 0 2px 0
          height 12px
          /*line-height 12px*/
          font-size 0
          .supports-icon
            /*display table-cell*/
            /*vertical-align middle*/
            display inline-block
            vertical-align top
            width 12px
            height 12px
            background-size 12px 12px
            &.decrease
              bg-img('decrease_1')
            &.discount
              bg-img('discount_1')
            &.guarantee
              bg-img('guarantee_1')
            &.invoice
              bg-img('invoice_1')
            &.special
              bg-img('special_1')
          .supports-text
            box-sizing border-box
            display inline-block
            /*display table-cell*/
            /*vertical-align middle*/
            margin-left 4px
            /*height 12px*/
            /*line-height 12px*/
            /*font-size 10px*/
            /*font-weight 200*/
            /*border-top 1px solid transparent*/
            line-height 24px
            font-size: 20px;
            transform: scale(0.5);
            transform-origin: 0% 0%;
      .support-more-btn
        position absolute
        right 12px
        bottom 15px
        padding 0 8px
        height 24px
        line-height 24px
        font-size 0
        /*transform: scale(0.5);*/
        /*transform-origin: 0% 0%;*/
        background-color rgba(0, 0, 0, .2)
        border-radius 14px
        .support-num
          /*border-top 1px solid transparent*/
          line-height 24px
          font-size 10px
        /*font-weight 200*/
        .icon-keyboard_arrow_right
          margin-left 2px
          line-height 24px
          font-size 10px
    .bulletin-wrapper
      position relative
      /*box-sizing border-box*/
      padding 0 22px 0 12px
      height 28px
      line-height 28px
      /*font-size 0*/
      white-space nowrap
      overflow hidden
      text-overflow ellipsis
      background-color rgba(7, 17, 27, .2)
      .bulletin-icon
        display inline-block
        vertical-align top
        margin-top 8px
        margin-right 4px
        width 22px
        height 12px
        background-size 22px 12px
        bg-img('bulletin')
      .bulletin-preview
        box-sizing border-box
        display inline-block
        margin-top 10px
        vertical-align: top;
        width calc(100% - 26px)
        height 12px
        font-size 10px
        line-height 12px
        overflow hidden
        text-overflow ellipsis
      .icon-keyboard_arrow_right
        position absolute
        right 10px
        line-height 28px
        font-size 10px

    .header-bg
      position absolute
      z-index -1
      top 0
      width 100%
      height 100%
      filter blur(5px)
      background-color rgba(7, 17, 27, .5)
      background-size contain
      background-repeat no-repeat
  /*asd*/
</style>
