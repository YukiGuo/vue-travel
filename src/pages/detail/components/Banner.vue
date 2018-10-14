
<template>
  <div>
  	<div class="banner">
  		<div class="img-wrapper" @click="handleClick">
  			<img class="img-content":src ="bannerImg">
  			<div class="img-info">
  			   <div class="img-title">{{this.sightName}}（AAAA景区）</div> 
                 <div class="img-num"><span class="iconfont ">&#xe648;&nbsp;&nbsp;&nbsp;{{this.gallaryImgs.length}}</span></div>
              </div> 
  		</div>
  		<div class="desc">
  			<div class="comment 
  			border-rightbottom ">
  			    <div class="right">
  					<p class="com1">
  						<span class="span1">4.9</span> 分&nbsp;&nbsp;很棒
  					</p>
  					<p class="com2">20348条评论 23条攻略</p>
  				</div>
  				<span class="iconfont right-arrow">&#xe601; </span>	
  			</div>
  			<div class="info border-bottom">
  			    <div class="left">	
  					<p class="text1">景点简介</p>
  					<p class="text2">开放时间、贴士</p>
  				</div>	
                  <span class="iconfont right-arrow">&#xe601; </span>
  			</div>
  			<div></div>
  		</div>
  	</div>
    <common-gallary 
      :imgs = "gallaryImgs" 
      v-show= "showGallary"
      @close ="closePic"
    ></common-gallary>
  </div>
</template>
<script >
import CommonGallary from'common/gallary/Gallary.vue'
	export default {
		name:'DetailBanner',
    props:{
           sightName:String,
           bannerImg:String,
           gallaryImgs:Array
    },
    data () {
      return {
        showGallary :false
      }
    },
    components :{
      CommonGallary
    },
    methods:{
      handleClick (){
        this.showGallary = true
      },
      closePic () {
         this.showGallary = false
      }
    }
	}
</script>
<style lang="stylus" scoped >
@import "~style/varibles.styl"
@import "~style/mixins.styl"
  .banner
    width:100%
    .img-wrapper
      width:100%
      position:relative
      overflow:hidden
      padding-bottom:55%
      height:0
      background-color:#ccc
      .img-content
        width:100%
      .img-info
        display:flex
        position:absolute
        bottom:0
        left:.2rem
        right:0
        line-height:.6rem
        background-image:linear-gradient(top,rgba(0,0,0,0),rgba(0,0,0,0.8))
        color:#fff        
      .img-title
        flex:1
        font-size:.32rem
        line-height:.68rem
        ellipsis()
      .img-num
        padding:0 .4rem
        margin-top:.16rem
        height:.32rem
        line-height:.32rem
        background-color:rgba(0,0,0,0.5)
        border-radius:.2rem
        font-size:.24rem
    .desc
      height:1rem
      padding:.16rem 
      .comment
        float:left
        width:50%
        height:100%
        .right
          float:left
          width:80%
	        .com1
	          color:orange
	          .span1
	            font-size:.5rem
	        .com2
	          font-size:.24rem
	          color:#ccc
	          line-height:.54rem
	    .right-arrow
	       width:19%
	       float:left
	       line-height:1rem
	       color:#aaa          
      .info
        box-sizing: border-box
        float:left
        width:50% 
        height:100%
        padding-left:.2rem
        .left
          width:80%
          float:left
        .text1
          line-height:.4rem
        .text2
          line-height:.68rem
          font-size:.25rem
          color:#ccc  

</style>