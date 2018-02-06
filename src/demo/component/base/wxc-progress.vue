<template>
    <div>
        <wxc-progress percent=60
                      bar-width=600
                      bar-height=40
                      bg-color="#ebebeb"
                      active-color="#0eadff"
                      text-color="#000000"
                      show-info="true"
        >
        </wxc-progress>
    </div>
</template>

<script>
    import {WxcProgress} from '../../../framework/component/index'

    export default {

        components: {
            "wxc-progress": WxcProgress
        },

        methods: {}
    }
</script>

<style scoped>


</style>