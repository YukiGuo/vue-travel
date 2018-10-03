<template>
	<div class="slider">
		<div class="slidershow">
			<li v-for ='(item,index) of img'
			>
				<img :src=item class="sliderimg">
			</li>
		</div>
		<div class="slide">
			<span class="iconfont left">&#xe624;</span>
			<span class="iconfont right">&#xe601;</span>
		</div>
		<div class="sliderbar">
			<div class="dot" v-for= '(item,index) of img'></div>
		</div>
	</div>
</template>
<script >
export default {
	name: 'HomeSwiper',
	data:function(){
		return {
		  img:[
		  '/static/img/sliderimg01.jpg',
		  '/static/img/sliderimg02.jpg',
		  '/static/img/sliderimg03.jpg',
		  '/static/img/sliderimg04.jpg',
		  '/static/img/sliderimg05.jpg',
		  ],
	    }
	},
	methods:{
       leftClick: function(){
       }
	}
}
setInterval(function(){
	console.log("hello");
},3000)
</script>
<style lang="stylus" scoped>
  li
    list-style:none
  .slider
    position:relative
    .slidershow
      overflow: hidden
      width:100%
      height:0
      padding-bottom: 25.67%
      .sliderimg
        width:100%
  .slide
    .left,.right
      position:absolute
      top:35px
      width:30px
      height:30px
      background-color:#ccc
      border-radius:50%
      opacity:0.5
      line-height:30px
      
    .left
      left:0
    .right
      right:0            
  .sliderbar
    .dot
      display:inline-block
      margin-right: 0.2rem
      width:0.15rem
      height:0.15rem
      border: solid 1px #ccc
      border-radius:50%
      background-color:#fff
</style>