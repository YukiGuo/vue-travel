<template>
<div class="wrapper">
	<input class="search" placeholder="输入城市名或拼音" v-model ="keyname">
  <div class="list-content"
     v-show ="keyname"
     ref = "content"
  >
    <ul>
      <li class="item border-bottom"
       v-for = "item of list" 
       :key ="item.id"
       @click ="handleClick(item.name)"
      >
        {{item.name}}
      </li>
      <li v-show = "listShow">没有找到匹配数据</li>
    </ul>
  </div>
</div>
</template>
<script >
import BScroll from 'better-scroll'
import{mapMutations} from'vuex'
export default { 
      name:'CitySearch',
      props:{
          city:Object
          },
      data () {
        return {
          keyname:'',
          timer:null,
          list:[]
        }
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
        keyname () {
          if (this.timer){
            clearTimeout(this.timer)
          }
          if (!this.keyname){
            this.list = []
            return
          }
          this.timer =setTimeout ( () =>{
             const result =[]
             for (let i in this.city){
              this.city[i].forEach ((value) => {
                if (value.spell.indexOf(this.keyname) > -1 || value.name.indexOf(this.keyname) >-1)
                {
                  result.push(value)
                }
              })
             }
             this.list = result
          },100)
        }
      },
      computed :{
        listShow () {
          return !this.list.length
        }
      },
      mounted () {
        this.scroll = new BScroll(this.$refs.content)
      }
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
    .list-content
      z-index:2
      position:absolute
      left:0
      right:0
      top:2.7rem
      bottom:0
      overflow:hidden
      background-color:#eee
      .item
        background-color:#fff
        line-height: .62rem
        padding-left:.2rem
      
</style>