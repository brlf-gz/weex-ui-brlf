<template>
    <div>
        <text class="cIcon" :style="{fontSize:fontSize,color:color}">{{Icon[name]}}</text>
    </div>
</template>

<script>
    var he = require('he');
    import Icon from "./iconName.js"
    var domModule = weex.requireModule("dom");
    export default {
        props:{
            name:
                {
                    default:"order",
                    type:String
                },//传入Icon名，Icon参考iconName.js
            fontSize:{default:"80px"},
            color:{default:"#da000f"},
        },
        name: "wxc-icon",
        data: () => ({
            Icon
        }),


        computed: {
            // getFontName: function() {
            //     return he.decode(this.name)
            // }
        },




        created (){
            domModule.addRule('fontFace',{
                'fontFamily':'iconfont',
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




