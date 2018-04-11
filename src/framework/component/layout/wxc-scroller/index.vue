<template>
    <scroller>
        <slot></slot>
        <loading class="footer" @loading="loadmore"></loading>
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
        max-height: 1px;
    }
</style>