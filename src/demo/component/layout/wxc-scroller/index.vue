<template>
    <div>
        <wxc-scroller :loadmore="onloadmore">
            <text v-for="item in list">{{item}}</text>
        </wxc-scroller>
    </div>
</template>

<script>
    import {WxcScroller} from '../../../../framework/component/index'

    export default {

        data() {
            return {
                list:[],
            }
        },

        created(){
            this.list = new Array(51)
                .join(0)
                .split('')
                .map((item, index) => {
                return index;
            });

        },

        components: {
            "wxc-scroller": WxcScroller,
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

<style scoped>

</style>