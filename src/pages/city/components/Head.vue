<template>
	<div class="header">
    <router-link to='/'>
      <span class="iconfont back">&#xe624;</span>
    </router-link>
		选择城市
	</div>
</template>
<script >
  export default { 
      name:'CityHead',
	}
</script>

<style lang ="stylus" scoped>
@import '~style/varibles.styl'
  .header
    position:relative
    width: 100%
    overflow: hidden
    height:$headHeight
    line-height:$headHeight
    background-color:$bgColor
    font-size:.32rem
    color:#fff
    text-align: center
    .back
      position:absolute
      top: 0
      left 0
      color:#fff
</style>