<template>
    <div>
       <wxc-row>
           <text>1</text>
           <text>2</text>
           <text>3</text>
       </wxc-row>
        <wxc-row>
            <text>1</text>
            <text>2</text>
            <text>3</text>
        </wxc-row>
        <wxc-row>
            <text>1</text>
            <text>2</text>
            <text>3</text>
        </wxc-row>
    </div>
</template>

<script>
    import {WxcRow} from '../../packages/index'

    export default {

        components: {
            'wxc-row': WxcRow,
        },

    }
</script>
