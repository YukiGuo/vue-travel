<template>
	<div class="wrapper">
		<p class="title">热销推荐</p>
		<ul>
			<li class="item border-bottom" v-for = "item of recommendList" :key ="item.id">
				<img class="img-content" :src="item.imgurl">
				<div class="info">
					<p class="info-name">{{item.name}}</p>
		            <p class="info-comment"><span class="iconfont">&#xe626;&#xe626;&#xe626;&#xe626;&#xe626;</span>{{item.comment}}</p> 
		            <p class="info-price"><span>￥<em>{{item.price}}</em></span> 起</p>
				</div>
			</li>
		</ul>
	</div>
</template>
<script >
export default {
    name:'HomeRecommend',
    props:{
      recommendList:Array
    }
} 

</script>
<style lang ='stylus' scoped>
  @import '~style/mixins.styl'
  .wrapper
    .title
       margin-top:.2rem
       line-height:.8rem
       background-color:#eee
       text-align:left
       padding-left:.2rem
    .item
      display:flex
      position:relative
      width:100%
      height:1.9rem
      overflow:hidden
     .img-content
        float:left
        width:1.7rem
        height:1.7rem
        padding:.1rem
      .info
        flex:1
        min-width:0
        text-align:left
        padding-left:.2rem
        .info-name
          font-size:.32rem
          font-weight:600
          line-height:.35rem
          margin-top:.4rem
          ellipsis()
        .info-comment
          line-height:.6rem
          color:#ccc
          span
            padding-right:.25rem
            color:orange
            font-size:.25rem
        .info-price
           span
             color:orange
             padding-right:.15rem
             em
               font-size:.35rem
</style>