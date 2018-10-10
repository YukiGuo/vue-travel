<template>
	<div>
	  <city-head></city-head>
	  <city-search></city-search>
    <city-list 
      :city="city" 
      :hot="hot"
      :letter="letter"
    ></city-list>
    <city-alphbet 
      :city="city"
      @change ="letterChange"
    ></city-alphbet>
	</div>  
</template>
<script >
import axios from 'axios'
import CityHead from './components/Head.vue'
import CitySearch from './components/Search.vue'
import CityList from './components/List.vue'
import CityAlphbet from './components/Alphbet.vue'
  export default { 
      name:'City',
      components: {
      	CityHead,
      	CitySearch,
        CityList,
        CityAlphbet
      },
      data () {
        return {
          city:{},
          hot:[],
          letter:''
        }
      },
      methods:{
        getCityInfo (){
          axios.get('/api/citylist.json').then(this.getCityInfoSucc)
        },
        getCityInfoSucc (res) {
          // console.log(res)
          // console.log(res.data)
          // console.log(res.data.data)
          // console.log(res.data.data.cities)
          res =res.data
          if (res.ret && res.data){
            this.city = res.data.cities
            this.hot = res.data.hotCities
          }
          else{
            alert("wrong")
          }
        },
        letterChange (g){
          this.letter =g

        }
      },
       mounted () {
        this.getCityInfo()
      },
	}
</script>

<style lang ="stylus" scoped>

</style>