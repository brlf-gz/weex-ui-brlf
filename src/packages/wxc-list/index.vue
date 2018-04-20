<template>
    <scroller v-if="isWeb">
        <refresh v-if="refresh !== undefined"
                 class="refresh"
                 @refresh="refresh"
                 :display="refreshDisplay ? 'show' : 'hide'">
            <text class="indicator-text">下拉刷新</text>
        </refresh>
        <slot/>
        <loading class="footer"
                 @loading="loadmore"></loading>
    </scroller>
    <list v-else
          @loadmore="loadmore">
        <refresh v-if="refresh !== undefined"
                 class="refresh"
                 @refresh="refresh"
                 :display="refreshDisplay ? 'show' : 'hide'">
            <text class="indicator-text">下拉刷新</text>
        </refresh>
        <slot/>
    </list>
</template>

<script>

    export default {
        name: "wxc-list",

        props: {
            loadmore:Function,
            refresh:Function,
            refreshDisplay:{
                type: Boolean,
                default: false
            }
        },

        data() {
            return {

            }
        },

        computed: {
            isWeb(){
               return weex.config.env.platform.toLowerCase() === 'web';
            }
        },

        method:{

        },
    }
</script>

<style scoped>
    .refresh {
        width: 750px;
        height: 100px;
        flex-direction: row;
        justify-content: center;
        align-items: center;
    }
    .indicator-text {
        color: #555555;
        font-size: 40px;
        text-align: center;
    }
    .footer{
        height: 1px;
        justify-content: center;
        align-items: center;
    }

</style>