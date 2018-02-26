<template>
  <ul class="rating-stars" :class="size">
    <li v-for="(item,index) in items" class="star-item" :class="item" :key="index"></li>
  </ul>
</template>

<script>
  export default {
    name: 'stars',
    props: {
      ratingNum: {
        type: Number
      },
      size: {
        type: Number
      }
    },
    data () {
      return {
        items: []
      }
    }
  }
</script>

<style lang="stylus" rel="stylesheet/stylus" scoped>
  .rating-stars
    font-size 0
    &.star-48
      .star-item
        display inline-block
        margin-right 20px
        width 20px
        height 20px

  /*asd*/
</style>
