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
	data (){
		return {
			weekendList:[
			{
				id:'001',
                imgurl:'http://img1.qunarzz.com/sight/source/1603/ad/69b0fc5f48ad5f.jpg_r_640x214_b0fd5c7b.jpg' ,
                name:'亲子时光TOP10',
                desc:'中西合璧，现代和传统各有各的精彩'  
			},
            {
				id:'002',
                imgurl:'http://img1.qunarzz.com/sight/source/1505/7d/df6ff468331c43.jpg_r_640x214_1f3783d0.jpg' ,
                name:'上海必游TOP10',
                desc:'走进自然或玩转乐园，感知大千世界'  
			},
			  {
				id:'003',
                imgurl:'http://img1.qunarzz.com/sight/source/1511/1d/fe098e8cfec117.jpg_r_640x214_a9be292a.jpg' ,
                name:'上海城市风光',
                desc:'来这里寻找你所认识的上海'  
			},
			]
		}
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