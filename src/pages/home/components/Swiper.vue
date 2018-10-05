<template>
	<div class="wrapper">
	  <swiper :options="swiperOption" >
	    <swiper-slide v-for = '(item) of swiperList ' :key ='item.id'>
	      <img class="swiper-img" 
	      :src='item.imgurl'> 
	    </swiper-slide>
        <div class="swiper-pagination"  slot="pagination"></div>
       </swiper>
	</div>
</template> 
<script >
export default {
	name: 'HomeSwiper',
	data () {
		return {
			swiperOption: {
				pagination: '.swiper-pagination',
				loop: true
			},
			swiperList: [
			{
				id: '001',
				imgurl: 'http://img1.qunarzz.com/piao/fusion/1809/31/da037478f37cf202.jpg_750x200_a02cf862.jpg'
			},
			{
				id: '002',
				imgurl: 'http://img1.qunarzz.com/piao/fusion/1809/8e/9ef61cb5e88b1302.jpg_750x200_31a50677.jpg'
			},
			{
				id: '003',
				imgurl: 'http://img1.qunarzz.com/piao/fusion/1809/82/c94c9a77de17f902.jpg_750x200_a8419488.jpg'
			},
			{
				id: '004',
				imgurl: 'http://img1.qunarzz.com/piao/fusion/1809/c6/2467595fffc3b302.jpg_750x200_cca13d51.jpg'
			},
			{
				id: '005',
				imgurl: 'http://img1.qunarzz.com/piao/fusion/1809/83/a77595fb02eed602.jpg_750x200_1627b072.jpg'
			}
			]
		}
	}
}	
</script>
<style lang="stylus" scoped>
.wrapper>>> .swiper-pagination-bullet-active
    background-color:#fff !important
.wrapper
    width:100%
    height:0
    overflow:hidden
    padding-bottom:26.5%
    background-color : #ccc
    .swiper-img
      width: 100%
  .swiper-img
     width:100% 
   
</style>