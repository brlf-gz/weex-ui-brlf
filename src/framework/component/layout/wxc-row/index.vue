<template>
    <div :class="['wxc-row-root',layout]"
         :style="{backgroundColor:bcolor}"
         @touchstart="onTouchstart"
         @touchend="onTouchend"
         @click="onClick"
         @touchcancel="onTouchend">
        <slot></slot>
    </div>
</template>

<script>
    export default {
        name: "wxc-row",
        props: {
            layout:{default:'center'},
            color: {default: "#ff0000"},
            touchColor: {default: "#ffff00"},
            isTouch:{default:'false'},
        },

        created: function () {
            this.bcolor = this.color;
        },

        data: function () {
            return {
                bcolor: "#ffffff",
            }
        },

        methods: {
            onClick : function(e){
               this.$emit("onClick");
            },

            onTouchstart: function (e) {
                if(this.isTouch=='true'){
                    this.bcolor = this.touchColor;
                }
            },

            onTouchend: function (e) {
                if(this.isTouch == 'true'){
                    this.bcolor = this.color;
                }
            },
        },
    }

</script>

<style scoped>
    .wxc-row-root{
        display: flex;
        flex-direction: row;
        justify-content: center;
    }

    .center{
        justify-content: center;
    }

    .left{
        justify-content: flex-start;
    }

    .right{
        justify-content: flex-end;
    }

    .between{
        justify-content: space-between;
    }

    .around{
        justify-content: space-around;
    }



</style>