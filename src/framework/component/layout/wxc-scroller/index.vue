<template>
    <scroller style="flex: 1;">
        <slot></slot>
        <loading class="footer" @loading="loadmore" :display="true ? 'display' : 'hide'"></loading>
    </scroller>
</template>

<script>

    export default {
        name: "wxc-scroller",

        props: {
            loadmore:Function,
        },

        data() {
            return {
                displayBool: 'show'
            }
        },

        computed: {

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