<template>
	<div class="wrapper">
		<div class="item border-bottom" v-for = "item of list">
           <span class="logo"></span>
		   {{item.title}}
	        <div v-if ="item.children">
	           <detail-list :list ="item.children"></detail-list>
	           <div class="info">
		          <div class="des">【上海出发】东方明珠+上海杜莎夫人蜡像馆+上海历史发展陈列馆+黄浦江游览1日游</div>
		            <div class="price">
		            	￥<span>258</span>
		            	起
		            </div>
	            </div>
	        </div>
		</div>
	</div>
</template>

<script >
	export default {
		name:"detailList",
		props:{
			list:Array
		}
	}
</script>

<style lang = "stylus" scoped>
@import "~style/mixins.styl"
.wrapper
  .item
    line-height:.8rem
    font-size:.32rem
    padding-left:.6rem
    .logo
      display:inline-block
      position:absolute
      top:.26rem
      left:.2rem
      width:.36rem
      height:.36rem
      background:url('https://s.qunarzz.com/piao/image/touch/sight/detail.png') 0 -.45rem no-repeat
      background-size:.4rem 3rem
      margin-right:.1rem
    .info
      height:1rem
      .des
        width:70%
        display:inline-block
        ellipsis()
       .price
         width:28%
         display:inline-block
         ellipsis()
         span
          color:orange
          font-size:.45rem
         

</style>