<template>
	<div>
		<detail-head></detail-head>
       <detail-banner></detail-banner>
       <div  class="content"></div>
</div>
</template>
<script >
import detailBanner from'./components/Banner.vue'
import detailHead from'./components/Head.vue'
	export default {
		name:'Detail',
		components:{
			detailBanner,
			detailHead
		}
	}
</script>
<style lang="stylus" scoped >
	.content
	  height:50rem
</style>