<template>
    <div>
        <wxc-list :loadmore="onloadmore"
                  :refresh="onrefresh"
                  :refreshDisplay="refreshDisplay">
            <cell v-for="item in list">
                <text>{{item}}</text>
            </cell>
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
            refreshDisplay: false,
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
            onrefresh(){
                this.refreshDisplay = true;
                setTimeout(() => {
                    this.list = [];
                    this.list = new Array(11)
                        .join(0)
                        .split('')
                        .map((item, index) => {
                            return index;
                        });
                    this.refreshDisplay = false
                }, 2000);

            },
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