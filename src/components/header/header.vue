<template>
  <div class="header">
    <div class="content-wrapper">
      <div class="avatar">
        <img width="64" height="64" :src="seller.avatar" alt="头像">
      </div>
      <div class="seller-content">
        <div class="title">
          <span class="brand"></span>
          <span class="seller-name"></span>
        </div>
        <p class="delivery">{{seller.description}}/{{seller.deliveryTime}}分钟送达</p>
        <div v-if="seller.supports" class="supports">
          <span class="supports-icon" :class="seller.supports[0].type"></span>
          <span class="supports-text">{{seller.supports[0].description}}</span>
        </div>
      </div>
      <div v-if="seller.supports" class="support-more-btn">
        <span class="support-num">{{seller.supports.length}}个</span>
        <i class="keyboard_arrow_right"></i>
      </div>
    </div>
    <div class="bulletin-wrapper"></div>
  </div>
</template>

<script>
  export default {
    name: 'v-header',
    props: {
      seller: {
        type: Object
      }
    }
  }
</script>

<style lang="stylus" rel="stylesheet/stylus">
  @import "../../common/stylus/mixin.styl"
  .header
    background-color rgba(7, 17, 27, .5)
    filter blur(10px)
    .content-wrapper
      padding 24px 12px 18 24
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
          padding-top 4px
          .brand
            bg-img('brand')

</style>
