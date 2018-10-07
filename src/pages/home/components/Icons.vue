<template>
	<div class="icons">
		<swiper :options="swiperOption">
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
  props:{
    iconsList: Array
  },
data () {
    return {
      swiperOption: {
       autoplay:false
      },
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
</style>