<template>
    <div>
        <wxc-scroller>
            <text v-for="i in 100">{{i}}</text>
        </wxc-scroller>
    </div>
</template>

<script>
    import {WxcScroller} from '../../../../framework/component/index'

    export default {

        data() {
            return {
            }
        },

        components: {
            "wxc-scroller": WxcScroller,
        },

        methods: {

        }
    }
</script>

<style scoped>

</style>