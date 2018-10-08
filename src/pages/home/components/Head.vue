<template>
	<div class="head">
	    <div class="headleft">
	    	<span class="iconfont">&#xe624;</span>
	    </div>
	    <div class="headinput">
            <span class="iconfont">&#xe632;</span> 
	    	输入城市/景点/游玩等主题
	    </div>
      <router-link to='/city'>
	      <div class="headright"> 
	        {{this.city}}
	        <span class="iconfont">&#xe6aa;</span>
	      </div>
      </router-link>  
	</div>
</template>
<script>
export default {
	name: 'HomeHead',
  props: {
    city: String
  }
}
</script>

<style lang="stylus" scoped>
  @import '~style/varibles.styl'
  .head
    display: flex
    line-height: $headHeight
    color: #fff
    background-color: $bgColor
    .headleft
      width: .64rem
      float: left
    .headinput
      flex:1
      height: .64rem
      line-height: .64rem
      margin-top: .12rem
      margin-bottom: .12rem
      padding-left:.2rem
      color: #ccc
      text-align:left
      background-color:#fff
      border-radius:.1rem
    .headright
       width: 1.24rem
       float: right
       text-align: center
       color:#fff
</style>
