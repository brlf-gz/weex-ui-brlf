<template>
    <div class="cProgress">
        <div :style="rootProgressStyle">
            <div class="cProgressBackground" :style="bgStyle"></div>
            <div :style="progressStyle"></div>
        </div>
        <text v-if="showInfo" :style="textStyle"> {{percent}}% </text>
    </div>
</template>

<script>
    export default {
        name: "wxc-progress",

        props: {
            percent: {default: 0, type: Number},
            barWidth: {default: 600, type: Number},
            barHeight: {default: 100, type: Number},
            bgColor: {default: "#ebebeb", type: String},
            activeColor: {default: "#0eadff", type: String},
            textColor: {default: "#000000", type: String},
            showInfo: {default: false, type: Boolean},
        },

        data() {

        },

        computed: {
            rootProgressStyle(){
                return {
                    width:this.barWidth + 'px',
                    height:this.barHeight + 'px'
                }
            },
            bgStyle(){
                return {
                    backgroundColor:this.bgColor
                }
            },
            progressStyle(){
                const {percent,barHeight, activeColor} = this;
                return {
                    width: (percent >= 0 && percent <= 100 ? percent : 0) + '%',
                    height: barHeight + 'px',
                    backgroundColor: activeColor
                }
            },
            textStyle(){
                return {
                    color:this.textColor,
                }
            },
        }
    }
</script>

<style scoped>
    .cProgress {
        flex-direction: row;
        align-items: center;
    }

    .cProgressBackground {
        position: absolute;
        top: 0;
        bottom: 0;
        left: 0;
        right: 0;
    }
</style>