<template>
    <div :style="{backgroundColor:bcolor}"
         @touchstart="onTouchstart"
         @touchend="onTouchend"
         @click="onClick"
         @touchcancel="onTouchend">
        <slot></slot>
    </div>
</template>

<script>
    export default {
        name: "wxc-touch-div",
        props: {
            color: {default: "white"},
            touchColor: {default: "#ffff00"},
        },

        data: function () {
            return {
                bcolor: "white",
            }
        },

        components: {},

        created: function () {
            this.bcolor = this.color;
        },

        methods: {
            onClick : function(e){
               this.$emit("onClick");
            },

            onTouchstart: function (e) {
                this.bcolor = this.touchColor;
            },

            onTouchend: function (e) {
                this.bcolor = this.color;
            },
        },
    }

</script>

<style scoped>

</style>