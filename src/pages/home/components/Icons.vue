<template>
	<div class="icons">
		<swiper>
			<swiper-slide v-for="(page,index) of pages" :key="index">
				<div class="icon" v-for="item of page">
				    <div class="icon-img">
					  <img class="icon-img-content" :src="item.imgurl" >
				    </div>
				    <p class="img-desc">{{item.desc}}</p>
			    </div>
			</swiper-slide>
		</swiper>
	</div>
</template>
<script >
export default {
	name:'HomeIcons',
	data () {
        return{
          iconsList:[
         	  {
        		id:'001',
        		imgurl:'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
        		desc:'景点门票'
        	  },
              {
            	id:'002',
            	imgurl:'http://img1.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png',
            	desc:'一日游'
              },
              {
            	id:'003',
            	imgurl:'http://img1.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png',
            	desc:'上海必游一样一样'
              },
              {
            	id:'004',
            	imgurl:'https://img1.qunarzz.com/piao/fusion/1803/20/831d62d2e1c7be02.png',
            	desc:'网红top榜'
              },
              {
            	id:'005',
            	imgurl:'http://img1.qunarzz.com/piao/fusion/1803/ea/01d081dacb03cc02.png',
            	desc:'赏秋色'
              },
              {
            	id:'006',
            	imgurl:'http://img1.qunarzz.com/piao/fusion/1805/57/1e29afd06f881102.png',
            	desc:'普陀山'
              },
              {
            	id:'007',
            	imgurl:'http://img1.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png',
            	desc:'上海必游'
              },
              {
            	id:'008',
            	imgurl:'https://img1.qunarzz.com/piao/fusion/1803/20/831d62d2e1c7be02.png',
            	desc:'网红top榜'
              },
              {
            	id:'009',
            	imgurl:'http://img1.qunarzz.com/piao/fusion/1803/ea/01d081dacb03cc02.png',
            	desc:'赏秋色'
              },  
            ]
        }
	},    
	computed:{
		pages () {
			const pages =[]
		    this.iconsList.forEach((item,index) =>{
                const page =Math.floor(index/8)
                if (!pages[page]){
                	pages[page]=[]
                }
                pages[page].push(item)
		    })
		    return pages
		}
	}
}
</script>
 
<style lang="stylus" scoped>
  @import "~style/mixins.styl"
  .icons
    overflow:hidden
    height:0
    padding-bottom:50%
    .icon
      position:relative
      overflow:hidden
      float:left
      width:25%
      height:0
      padding-bottom:25%
      .icon-img
        position:absolute
        top:0
        left:0
        right:0
        bottom:.44rem
        .icon-img-content
          height:100%
          margin:auto
          padding:.1rem
       .img-desc
          position:absolute
          bottom:0
          left:0
          right:0
          text-align:center
          line-height:.44rem
          ellipsis ()
          overflow:hidden
          white-space:nowrap
          text-overflow:ellipsis
</style>