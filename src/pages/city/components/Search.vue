<template>
<div class="wrapper">
	<input class="search" placeholder="输入城市名或拼音">
</div>
</template>
<script >
export default { 
      name:'CitySearch',
	}
</script>

<style lang ="stylus" scoped>
@import '~style/varibles.styl'
  .wrapper
    height:.72rem
    background-color:$bgColor
    padding:0 .1rem
    .search
      box-sizing:border-box
      width:100%
      height:.62rem
      padding:0 .1rem
      line-height:.62rem
      border-radius:.06rem
      text-align:center
      color:#666
</style>