<template>
    <div>
     <home-head></home-head>
     <home-swiper></home-swiper>
     <home-icons></home-icons>
    </div>
</template>
<script>
import HomeHead from './components/Head.vue'
import HomeSwiper from './components/Swiper.vue'
import HomeIcons from './components/Icons.vue'
export default {
  name: 'Home',
  components: {
    HomeHead,
    HomeSwiper,
    HomeIcons
  }
}
</script>
<style lang ="stylus" scoped>

</style>
