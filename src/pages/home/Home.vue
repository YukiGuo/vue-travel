<template>
    <div>
     <home-head ></home-head>
     <home-swiper :swiperList="swiperList"></home-swiper>
     <home-icons :iconsList="iconsList"></home-icons>
     <home-recommend :recommendList="recommendList"></home-recommend>
     <home-weekend :weekendList="weekendList"></home-weekend>

    </div>
</template>
<script>
import {mapState} from 'vuex'
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
        lastCity:'',
        swiperList:[],
        iconsList:[],
        recommendList:[],
        weekendList:[]
    }
  },
  computed :{
    ...mapState(['city'])
  },
  methods: {
    getHomeInfo (){
        axios.get('/static/mock/index.json?city='+this.city).then(this.getHomeInfoSucc)
    },
    getHomeInfoSucc (res){
       console.log(res)
       res =res.data
       if (res.data){
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
  mounted () {
    this.lastCity = this.city
    this.getHomeInfo()
    console.log('moubted')
  },
  activated () {
    if (this.lastCity !== this.city){
      this.city = this.lastCity
      this.getHomeInfo()
    }
    console.log('activated')
  }
}
</script>
<style lang ="stylus" scoped>

</style>
