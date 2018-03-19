<template>
    <div class="cRoot">
        <div>
            <text>设置点击效果</text>
            <wxc-touch-div class="cTouchDiv"
                   color="#ff0000"
                   touch-color="#ff8800">
                <text class="cText">Click Me</text>
            </wxc-touch-div>
        </div>

        <div style="margin-top:60px">
            <text>添加点击事件</text>
            <wxc-touch-div class="cTouchDiv"
                   color="#ff0000"
                   @onClick="onClick('one')"
                   touch-color="#ff8800">
                <text class="cText">Click Me</text>
            </wxc-touch-div>
        </div>

        <div style="margin-top:60px">
            <text>事件的传递:问题是点击second，底部div会接受touch事件</text>
            <wxc-touch-div class="cTouchDiv"
                   color="#ff0000"
                   @onClick="onClick('two-first')"
                   touch-color="#ff8800">
                <div class="cTouchDiv-div"
                    @click="onClick('two-second')">
                    <text>second</text>
                </div>
            </wxc-touch-div>
        </div>

        <div style="margin-top:60px">
            <text>事件的传递:覆盖touch事件:在html5有效</text>
            <wxc-touch-div class="cTouchDiv"
                   color="#ff0000"
                   @onClick="onClick('third-first')"
                   touch-color="#ff8800">
                <div class="cTouchDiv-div"
                    @touchstart="onTouchstart"
                    @touchend="onTouchend"
                    @touchcancel="onTouchend"
                    @click="onClick('third-second')">
                    <text>third</text>
                </div>
            </wxc-touch-div>
        </div>
    </div>
</template>

<script>
    import {WxcTouchDiv} from '../../../../framework/component/index'

    var modal = weex.requireModule('modal')
    export default {
        name: "wxc-touch-div",

        components: {
            "wxc-touch-div": WxcTouchDiv
        },

        methods: {
            onClick(param,e) {
                modal.toast({
                    message: 'click:' + param,
                    duration: 1
                })
            },

            onTouchstart: function (e) {
                e.stopPropagation()
            },

            onTouchend: function (e) {
                e.stopPropagation()
            },
        }
    }
</script>

<style scoped>

    .cRoot{
        width: 750px;
        display: flex;
        flex-direction: column;
    }

    .cTouchDiv{
        width: 750px;
        height: 200px;
        display: flex;
        flex-direction: row;
        justify-content: center;
    }

    .cTouchDiv-div{
        width: 150px;
        height: 150px;
        background-color: green;
        align-self: center;
    }

    .cText {
        align-self: center;
    }


</style>