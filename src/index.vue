<template>
    <div>
        <wxc-scroller :loadmore="onloadmore">
            <text v-for="item in list">{{item}}</text>
        </wxc-scroller>
    </div>
</template>

<script>
    import WxcScroller from "./framework/component/layout/wxc-scroller/index.vue";

    export default {
        components: {WxcScroller},
        data: () => ({
            list:[],
        }),
        created(){
            this.list = new Array(51)
                .join(0)
                .split('')
                .map((item, index) => {
                    return index;
                });
        },
        methods: {
            onloadmore(){
                for (let i = 0; i < 20; i++){
                    this.list.push(this.list.length)
                }
            }
        }
    }
</script>

<style>
    .wrapper {
        align-items: center;
        margin-top: 120px;
    }

    .title {
        padding-top: 40px;
        padding-bottom: 40px;
        font-size: 48px;
    }

    .logo {
        width: 360px;
        height: 156px;
    }

    .desc {
        padding-top: 20px;
        color: #888;
        font-size: 24px;
    }
</style>