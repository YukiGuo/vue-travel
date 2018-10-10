<template>
<div>
  <ul class="list" >
    <li 
      class="item" v-for = "item of letters" 
      :key="item"
      :ref ="item"
      @click ="handleclick"
      @touchstart ="handleTouchStart"
      @touchmove ="handleTouchMove"
      @touchend ="handleTouchEnd"
    >{{item}}</li>
  </ul>
</div> 
</template>
<script >
  export default { 
      name:'CityAlphbet',
      props:{
        city:Object
      },
      data () {
        return{
          touchStatus: false,
          startY: 0,
          timer: null
        }
      },
      computed : {
        letters () {
          const letters = []
          for(let i in this.city ){
            letters.push(i)
          }
          return letters
        }
      },
      updated () {
        this.startY =  this.$refs['A'][0].offsetTop
      },
      methods :{
        handleclick (e){
          console.log(e.target.innerText)
          this.$emit("change",e.target.innerText)
        },
        handleTouchStart () {
          this.touchStatus = true
        },
        handleTouchMove (e) {
          if (this.touchStatus ){
            if (this.timer){
              clearTimeout(this.timer)
            }
            else{
              const touchY = e.touches[0].clientY-134
              const index =Math.floor((touchY-this.startY)/20)
              if(index >= 0 && index<=this.letters.length){
                this.$emit('change',this.letters[index])
              }
            }  
          }
        },
        handleTouchEnd () {
          this.touchStatus = false
        }
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