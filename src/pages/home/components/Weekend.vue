<template>
	<div>
		<div class="title">周末去哪儿</div>
		<div class="item" v-for="item of weekendList" :key ="item.id">
			<img class="img-content" :src="item.imgurl">
			<div class="info">
				<p class="item-name">{{item.name}}</p>
			    <p class="item-desc">{{item.desc}}</p>
			</div>
		</div>
	</div>
</template>

<script >
export default {
	name:"HomeWeekend",
  props:{
      weekendList:Array
  }
}
</script>
<style lang="stylus" scoped>
   .title
      line-height:0.8rem
      background-color:#eee
      padding-left:.2rem
    .item
       .img-content
         width:100%
         height:36.8%
       .info
         padding-left:.2rem
         .item-name
           font-size:.24rem
           line-height:.48rem
         .item-desc
           margin-bottom:.1rem
           font-size:.2rem
        
</style>