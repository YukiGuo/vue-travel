<template>
    <div>
     <home-head></home-head>
     <home-swiper></home-swiper>
    </div>
</template>
<script>
import HomeHead from './components/Head.vue'
import HomeSwiper from './components/Swiper.vue'
export default {
  name: 'Home',
  components: {
    HomeHead,
    HomeSwiper
  }
}
</script>
<style lang ="stylus" scoped>

</style>
