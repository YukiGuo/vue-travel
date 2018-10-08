<template>
	<div>
	  <city-head></city-head>
	  <city-search></city-search>
	</div>  
</template>
<script >
import CityHead from './components/Head.vue'
import CitySearch from './components/Search.vue'
  export default { 
      name:'City',
      components: {
      	CityHead,
      	CitySearch
      }
	}
</script>

<style lang ="stylus" scoped>

</style>