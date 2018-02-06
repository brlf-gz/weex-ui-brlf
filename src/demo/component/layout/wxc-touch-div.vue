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
    import {WxcTouchDiv} from '../../../framework/component/index'

    export default {

        components: {
            "wxc-touch-div": WxcTouchDiv
        },

        methods: {
            onClick(e) {
                console.log("click me")
            }
        }
    }
</script>

<style scoped>
    .cTouchDiv {
        width: 200px;
        height: 200px;
        margin-left: 100px;
        margin-top: 100px;
        display: flex;
        flex-direction: row;
        justify-content: center;
    }

    .cText {
        align-self: center;
    }


</style>