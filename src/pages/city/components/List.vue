<template>
	<div class="wrapper" ref="wrapper">
    <div>
      <div class="area">
        <div class="title border-topbottom">当前城市</div>
        <div class="button-list">
          <div class="button-wrapper">
             <div class="button">
               {{this.currentCity}}
             </div>
          </div>
        </div>
      </div>
      <div class="area">
        <div class="title border-topbottom">热门城市</div>
          <div class="button-list">
            <div class="button-wrapper" 
              v-for ="item of hot" 
              :key ="item.id"
              @click ="handleClick(item.name)"
            >
               <div class="button">{{item.name}}</div>
            </div>                                        
          </div>
      </div>
      <div class="area" v-for ="(item,key) of city" :key="key" :ref ="key">
        <div class="title border-topbottom">{{key}}</div>
        <div class="item-list">
          <div class="item border-bottom"
            v-for = "innerItem of item" 
            :key ="innerItem.id"
            @click ="handleClick(innerItem.name)"
          >{{innerItem.name}}</div>
        </div>
      </div>
    </div>    
	</div>  
</template>
<script >
import BScroll from 'better-scroll'
import {mapState,mapMutations} from 'vuex'
  export default { 
      name:'CityList',
      props:{
        city:Object,
        hot:Array,
        letter:String
      },
      mounted (){
        this.scroll = new BScroll(this.$refs.wrapper)
      },
      methods :{
        handleClick (city ){
          // this.$store.dispatch('change',city)
          this.change(city)
          this.$router.push('/')   
        },
        ...mapMutations(['change'])
      },
      watch: { 
        letter () {
            if (this.letter){
              const element = this.$refs[this.letter][0]
              this.scroll.scrollToElement(element)
            }
          }
        },
      computed :{
        ...mapState ({
           currentCity:'city'
        })
      }     
      
	}
</script>

<style lang ="stylus" scoped>
  .border-topbottom
    &:before
      border-color:#CCC
    &:after
      border-color:#ccc
  .border-bottom
    &:before
      border-color:#ccc
  .wrapper
    overflow:hidden
    position:absolute
    top:2.8rem
    left:0
    bottom:0
    right:0
    .title
      line-height:.5rem
      background-color:#eee
      padding-left:.2rem
      font-size:.26rem
      color:#666
    .button-list
      padding:.1rem .6rem .1rem .1rem
      overflow:hidden
      .button-wrapper
        float:left
        width:33%
        .button
          margin:.1rem
          padding:.1rem 0
          text-align:center
          border:.02rem #ccc solid
          border-radius:.06rem
    .item-list
      .item
        padding-left:.2rem
        line-height:.7rem
</style>