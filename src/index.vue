<template>
    <div>
        <wxc-list :loadmore="onloadmore">
            <text v-for="item in list">{{item}}</text>
        </wxc-list>
    </div>
</template>

<script>

    import {WxcList} from "./packages/index";

    export default {
        components: {
            WxcList
        },
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

</style>