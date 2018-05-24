<template>
    <div>
        <div class="example">
            <text class="label">normal</text>
            <wxc-switch></wxc-switch>
        </div>
        <div class="example">
            <text class="label">checked</text>
            <wxc-switch checked="true"></wxc-switch>
        </div>
        <div class="example">
            <text class="label">disabled</text>
            <wxc-switch disabled="true" checked="true"></wxc-switch>
            <wxc-switch disabled="true"></wxc-switch>
        </div>
        <div class="example">
            <text class="label">onchange</text>
            <wxc-switch @change="onchange"></wxc-switch>
            <text class="info">{{checked}}</text>
        </div>
        <div class="example">
            <text class="label">size: 200px*50px</text>
            <wxc-switch width="200px" height="50px"></wxc-switch>
        </div>
    </div>
</template>

<script>
    import {WxcSwitch} from '../../packages/index'

    export default {

        components: {
            'wxc-switch': WxcSwitch,
        },

        data () {
            return {
                checked: false
            }
        },
        methods: {
            onchange (event) {
                console.log(`onchange, value: ${event.value}`);
                this.checked = event.value
            }
        }

    }
</script>

<style>
    .example {
        flex-direction: row;
        justify-content: flex-start;
        align-items: center;
        margin-top: 60px;
    }
    .label {
        font-size: 40px;
        line-height: 60px;
        width: 350px;
        color: #666;
        text-align: right;
        margin-right: 20px;
    }
    .info {
        font-size: 30px;
        line-height: 60px;
        color: #BBB;
        margin-left: 10px;
    }
</style>