<template>
    <scroller class="cRoot">
        <text>用途1:用来做内存嵌套</text>
        <text>用途2:用来图片的点击背景</text>
        <wxc-row class="cRow">
            <text class="cText">wxc-row-center</text>
        </wxc-row>
        <wxc-row class="cRow" 
            is-touch='true'
            layout="left">
            <text class="cText">wxc-row-left,touch effect</text>
        </wxc-row>
        <wxc-row class="cRow" layout="right">
            <text class="cText">wxc-row-right</text>
        </wxc-row>
        <wxc-row class="cRow" layout="right">
            <text class="cText" style="margin-right:20px">wxc-row-right multi</text>
            <text class="cText">wxc-row-right multi</text>
        </wxc-row>
        <wxc-row class="cRow" layout="between">
            <text class="cText" style="margin-right:20px">wxc-row-right multi</text>
            <text class="cText">wxc-row-right multi</text>
        </wxc-row>
        <wxc-row class="cRow" layout="around">
            <text class="cText" style="margin-right:20px">wxc-row-right multi</text>
            <text class="cText">wxc-row-right multi</text>
        </wxc-row>
    </scroller>
</template>

<script>
    import {WxcRow} from '../../../../framework/component/index'
    var modal = weex.requireModule('modal')
    export default {
        name: "wxc-row",

        components: {
            "wxc-row": WxcRow
        },

        methods: {
            onClick(param,e) {
                modal.toast({
                    message: 'click:' + param,
                    duration: 1
                })
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

    .cRow{
        width: 750px;
        height: 200px;
        margin-top: 60px;
    }

    .cText {
        align-self: center;
        width: 200px;
        height: 80px;
        background-color: yellow;
    }


</style>