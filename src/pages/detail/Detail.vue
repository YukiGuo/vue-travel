<template>
	<div>
		<detail-head></detail-head>
        <detail-banner   
          :sightName ="sightName"
          :bannerImg = "bannerImg"
          :gallaryImgs ="gallaryImgs"
         ></detail-banner>
        <detail-list 
          :list ="list"
        ></detail-list>
        <div  class="content"></div>
</div>
</template>
<script >
import detailBanner from'./components/Banner.vue'
import detailHead from'./components/Head.vue'
import detailList from'./components/List.vue'
import axios from'axios'
	export default {
		name:'Detail',
		components:{
			detailBanner,
			detailHead,
			detailList
		},
		data () {		
             return {
               list:[],
               sightName:'',
               bannerImg:'',
               gallaryImgs:[]
             }
		},
		methods : {
			getHomeInfo () {
				axios.get('/static/mock/detail.json',{
					params:{
						id:this.$route.params.id
					}
				}).then(this.getHomeInfoSucc)
			},
		    getHomeInfoSucc (res) {
		       if (res.data.data){
		       this.sightName =	res.data.data.sightName
		       this.list =res.data.data.categoryList
		       this.bannerImg =res.data.data.bannerImg
		       this.gallaryImgs=res.data.data.gallaryImgs
		       console.log(this.list)
		   }
		    }	
		},
		mounted () {
			this.getHomeInfo()
		}
	}
</script>
<style lang="stylus" scoped >
	.content
	  height:50rem
</style>