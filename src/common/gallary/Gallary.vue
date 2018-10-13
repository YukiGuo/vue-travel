<template>
	<div class="wrapper" @click ="handleClick">
		<div class="img-wrapper">
			<swiper :options ="swiperOptions">
				<swiper-slide v-for = "item of imgs">
					<img :src="item">
				</swiper-slide>
			</swiper>			
		</div>
		<div class=" swiper-pagination des" slot = "pagination">1/39</div>
	</div>
</template>

<script >
	export default {
		name:'CommonGallary',
		props:{
			imgs:{
				type:Array,
				default () {
					return 
					     []
				}
			}			
		},
		data () {
			return {
				swiperOptions: {
					pagination:'.swiper-pagination',
					paginationType:'fraction',
					observeParents:true,
					observer:true
				},

			}
		},
		methods: {
			handleClick (){
				this.$emit('close')
			}
		}
	}
</script>
<style lang = 'stylus' scoped>
.wrapper
   display:flex
   flex-direction:column
   position:fixed
   justify-content:center
   top:0
   left:0
   right:0
   bottom:0
   background-color:#000
   .img-wrapper
     height:0
     overflow:hidden
     padding-bottom:60%
     img
       width:100% 
   .des
     position:absolute
     left:0
     right:0
     bottom:.6rem
     color:#fff
     text-align:center   


</style>
