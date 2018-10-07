<template>
    <div>
     <home-head :city ="city"></home-head>
     <home-swiper :swiperList="swiperList"></home-swiper>
     <home-icons :iconsList="iconsList"></home-icons>
     <home-recommend :recommendList="recommendList"></home-recommend>
     <home-weekend :weekendList="weekendList"></home-weekend>

    </div>
</template>
<script>
import HomeHead from './components/Head.vue'
import HomeSwiper from './components/Swiper.vue'
import HomeIcons from './components/Icons.vue'
import HomeRecommend from './components/Recommend.vue'
import HomeWeekend from './components/Weekend.vue'
import axios from 'axios'
export default {
  name: 'Home',
  components: {
    HomeHead,
    HomeSwiper,
    HomeIcons,
    HomeRecommend,
    HomeWeekend
  },
  data () {
    return {
        city:' ',
        swiperList:[],
        iconsList:[],
        recommendList:[],
        weekendList:[]
    }
  },
  methods: {
    getHomeInfo (){
        axios.get('/static/mock/index.json').then(this.getHomeInfoSucc)
    },
    getHomeInfoSucc (res){
       console.log(res)
       res =res.data
       if (res.data){
          this.city = res.data.city
          this.iconsList = res.data.iconsList
          this.recommendList = res.data.recommendList
          this.swiperList = res.data.swiperList
          this.weekendList = res.data.weekendList
         }
        else {
            alert("cuowu")
        } 
    },
  } ,
  mounted (){
    this.getHomeInfo()
  }
}
</script>
<style lang ="stylus" scoped>

</style>
