<template>
    <div class="root">
        <wxc-progress class="progress"
               :percent=percent
               :bar-width=barWidth
               :bar-height=barHeight
               :bg-color=bgColor
               :active-color=activeColor
               :text-color=textColor
               :show-info=showInfo
        >
        </wxc-progress>
        <div class="divider"></div>
        <div class="attr-div">
            <text class="attr-text">进度百分比%</text>
            <input class="attr-input" placeholder="percent" @change="onChangePercent"/>
        </div>
        <div class="divider"></div>
        <div class="attr-div">
            <text class="attr-text">宽度</text>
            <input class="attr-input" placeholder="bar-width" @change="onChangeBarWidth"/>
        </div>
        <div class="divider"></div>
        <div class="attr-div">
            <text class="attr-text">高度</text>
            <input class="attr-input" placeholder="bar-height" @change="onChangeBarHeight"/>
        </div>
        <div class="divider"></div>
        <div class="attr-div">
            <text class="attr-text">背景颜色</text>
            <input class="attr-input" placeholder="bg-color" @change="onChangeBgColor"/>
        </div>
        <div class="divider"></div>
        <div class="attr-div">
            <text class="attr-text">进度条颜色</text>
            <input class="attr-input" placeholder="active-color" @change="onChangeActiveColor"/>
        </div>
        <div class="divider"></div>
        <div class="attr-div">
            <text class="attr-text">文字颜色</text>
            <input class="attr-input" placeholder="text-color" @change="onChangeTextColor"/>
        </div>
        <div class="divider"></div>
        <div class="attr-div">
            <text class="attr-text">下载进度（显示/隐藏）</text>
            <switch @change="onChangeShowInfo"></switch>
        </div>
        <div class="divider"></div>
    </div>
</template>

<script>
    import {WxcProgress} from '../../../../framework/component/index'

    export default {

        data() {
            return {
                percent: 0,
                barWidth: 600,
                barHeight: 40,
                bgColor: "#ebebeb",
                activeColor: "#0eadff",
                textColor: "#000000",
                showInfo: false,
            }
        },

        components: {
            "wxc-progress": WxcProgress,
        },

        methods: {
            onChangePercent(input) {
                this.percent = input.value;
            },
            onChangeBarWidth(input) {
                this.barWidth = input.value;
            },
            onChangeBarHeight(input) {
                this.barHeight = input.value;
            },
            onChangeBgColor(input) {
                this.bgColor = input.value;
            },
            onChangeActiveColor(input) {
                this.activeColor = input.value;
            },
            onChangeTextColor(input) {
                this.textColor = input.value;
            },
            onChangeShowInfo(event) {
                this.showInfo = event.value;
            },
        }
    }
</script>

<style scoped>
    .progress {
        margin: 40px;
    }

    .divider {
        width: 750px;
        height: 1px;
        background-color: #dcdcdc;
    }

    .attr-div {
        height: 100px;
        flex-direction: row;
        justify-content: space-between;
        align-items: center;
        padding: 0 20px;
    }

    .attr-text {
        font-size: 36px;
        color: black;
    }

    .attr-input {
        width: 200px;
        height: 56px;
        font-size: 36px;
        color: black;
        text-align: end;
    }
</style>