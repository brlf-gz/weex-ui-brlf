<template>
    <div>
        <wxc-list :loadmore="onloadmore">
            <cell v-for="item in list">
                <text>{{item}}</text>
            </cell>
        </wxc-list>
    </div>
</template>

<script>
    import {WxcList} from '../../packages/index'

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
            "wxc-list": WxcList,
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