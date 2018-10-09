<template>
<div>
  <ul class="list" >
    <li class="item" v-for = "(item,key) of city" :key="key">{{key}}</li>
  </ul>
</div> 
</template>
<script >
  export default { 
      name:'CityAlphbet',
      props:{
        city:Object
      }
	}
</script>

<style lang ="stylus" scoped>
@import "~style/varibles.styl"
  .list
    display:flex
    flex-direction:column
    justify-content:center
    position:absolute
    top:2.8rem
    right:0
    bottom:0
    width:.4rem
    .item
      line-height:.4rem
      color:$bgColor
      text-align:center


</style>