<template>
  <div class="cart-control">

    <transition name="move">
      <div class="cart-decrease" @click.stop="decreaseCart" v-show="food.count > 0">
        <i class="inner iconfont icon-decrease"></i>
      </div>
    </transition>

    <div class="cart-count" v-show="food.count > 0">{{ food.count }}</div>
    <div class="cart-add" @click.stop="addCart">
      <i class="iconfont icon-add"></i>
    </div>
  </div>
</template>

<script>
export default {
  props:{
    food:{
      type:Object
    }
  },
  methods:{
    addCart(){
      if(!this.food.count){
        // this.food.count = 1
        this.$set(this.food,'count',1)
      }else{
        this.food.count++
      }
      console.log(this.food.count);
    },
    decreaseCart(){
      if(this.food.count){
        this.food.count--;
        console.log(this.food.count);
      }
    }
  }
}
</script>

<style lang="stylus" scoped>
.cart-control
  font-size 0
  display: flex
  align-items: center
  .cart-decrease
    display inline-block
    padding 6px
    opacity 1
    transform translate3d(0, 0, 0)
    .inner
      display inline-block
      font-size: 20px
      line-height 20px
      color rgb(0, 160, 220)
      transition all .4s linear
      transform rotate(0)
    &.move-enter-active, &.move-leave-active
      transition all 0.4s linear
    &.move-enter, &.move-leave-to
      opacity 0
      transform translate3d(24px, 0, 0)
      .inner
        transform rotate(180deg)
  .cart-count
    display inline-block
    width 12px
    line-height 24px
    text-align center
    font-size 10px
    color rgb(147, 153, 159)
    vertical-align top
  .cart-add
    display inline-block
    padding 6px
    color rgb(0, 160, 220)
    .icon-add
      font-size: 24px
</style>
