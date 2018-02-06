<template>
    <div>
        <wxc-touch-div class="cTouchDiv"
                       color="#ff0000"
                       @click="onClick"
                       touch-color="#ff8800">
            <text class="cText">hello</text>
        </wxc-touch-div>
    </div>
</template>

<script>
  export default {
    name:"wxc-touch-div",

      components:{
        "wxc-touch-div" : require("../../../framework/component/layout/wxc-touch-div.vue")
      },

      methods:{
          onClick(e){
              console.log("click me")
          }
      }
  }
</script>

<style scoped>
    .cTouchDiv{
        width: 200px;
        height: 200px;
        margin-left: 100px;
        margin-top: 100px;
        display: flex;
        flex-direction: row;
        justify-content: center;
    }

    .cText{
        align-self: center;
    }


</style>