<template>
    <text class="cIcon" :style="{fontSize:fontSize}" v-html="Icon[name]"></text>
</template>

<script>
    import Icon from "./iconName.js"
    var domModule = weex.requireModule("dom");
    export default {
        props:{
            name:{default:"homepageSelect"},//传入Icon名，Icon参考iconName.js
            fontSize:{default:"80px"},
        },
        name: "wxc-icon",
        data: () => ({
            Icon
        }),


        created (){
            domModule.addRule('fontFace',{
                'fontFamily':'iconfont',   //注意这里必须是驼峰命名，跟上面的css样式对照
                'src':"url('//at.alicdn.com/t/font_565340_rp6941lhitvp9zfr.ttf')"
            })
        },
    }



</script>

<style scoped>
    .cIcon{
        font-family:iconfont
    }

</style>