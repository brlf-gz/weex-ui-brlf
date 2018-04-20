<template>
    <scroller v-if="isWeb">
        <slot/>
        <loading class="footer"
                 @loading="loadmore"></loading>
    </scroller>
    <list v-else
          @loadmore="loadmore">
        <slot/>
    </list>
</template>

<script>

    export default {
        name: "wxc-list",

        props: {
            loadmore:Function,
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
    .footer{
        height: 1px;
        justify-content: center;
        align-items: center;
    }
</style>