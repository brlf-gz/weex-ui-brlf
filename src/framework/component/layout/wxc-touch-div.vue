<template>
    <div :style="{backgroundColor:bcolor}"
        @touchstart="onTouchstart"
        @touchend="onTouchend"
        @touchcancel="onTouchend">
        <slot></slot>
    </div>
</template>

<script>
  export default {
      name:"wxc-touch-div",
      props:{
          color:{default:"white"},
          touchColor:{default:"#ffff00"},
          index:0
      },

      data:function(){
          return {
              bcolor:"white",
          }
      },

      components:{},

      created:function(){
          this.bcolor = this.color;
      },

      methods:{
          //onClick : function(e){
          //    var param ={
          //        index:this.index
          //    }
          //    this.$emit("onClick",param);
          //},

          onTouchstart:function(e){
              this.bcolor = this.touchColor;
          },

          onTouchend:function(e){
              this.bcolor = this.color;
          },
      },
  }

</script>

<style scoped>

</style>