<template>
<div class="header">
	<div class="title" v-show ="showTitle" :style ="opacityStyle">		
		<router-link 
		   tag = "span" 
		   class="iconfont back-icon"
		   to='/'
		 >
		&#xe624;</router-link>
	<span>上海杜莎夫人蜡像馆</span>
	</div>
	<router-link tag="div" to='/' class="back" 
	v-show ="!showTitle">
		<span class="iconfont ">&#xe624;</span>
   	</router-link>
</div>	
</template>
<script >
	export default {
		name:'detailHead',
		data () {
			return {
				showTitle:false,
				opacityStyle:{
					opacity:0
				}
			}
		},
		methods: {
          handleScroll () {
            const top = document.documentElement.scrollTop||document.body.scrollTop
            console.log(top)
            if (top>40) {
               let opacity = top/140
               opacity = opacity >1? 1:opacity
               this.opacityStyle ={
               	opacity:opacity
               }
                this.showTitle = true
               }
            else{
            	this.showTitle = false
              }   
            }
		},
		activated (){
			window.addEventListener('scroll',this.handleScroll)
		}
	}
</script>
<style lang='stylus' scoped>
@import "~style/varibles.styl"
    .header
      position:relative
      text-align:center
      color:#fff
      .back
        z-index:2
        position:absolute
        left:0.2rem
        right:0
        top:0.2rem
        height:.8rem
        line-height:.8rem
        width:.8rem
        background-color:rgba(0,0,0,0.5)
        border-radius:100%
        .iconfont
          font-size:.36rem
      .title
        z-index:3
        overflow:hidden
        position:fixed
        top:0
        left:0
        right:0
        bottom:0
        font-size:.35rem
        height:.84rem
        line-height:.84rem
        background-color:$bgColor
        .back-icon
          position:fixed
          left:0
          font-size:.36rem
</style>