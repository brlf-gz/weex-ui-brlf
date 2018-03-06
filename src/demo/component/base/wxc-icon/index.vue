<template>
    <div>
        <text class="cTextTitle">选择下拉框里的值更改图标</text>
        <div class="cIconCenterDiv">
            <icon-text class="cIconText" :fontSize="200" :name="name"></icon-text>
            <div class="cSelectDiv">
                <text class="cSelectText">{{name}}</text>
                <image class="cImg" @click="onClickSelectImg"></image>
            </div>
            <scroller class="cSelectFrameDiv" v-if="isSelectShow">
                <div class="cSelectCellDiv" v-for="(item,index) in nameItem" @click="onSelectCellClick(index)">
                    <text class="cCellEnglish">{{item.name}}</text>
                    <text class="cCellEnglish">{{item.text}}</text>
                </div>
            </scroller>
        </div>
    </div>



</template>


<script>

    export  default {
        data(){
            return{
                isSelectShow:true,
                name:"refresh",
                nameItem:[
                    {name:"refresh",text:"刷新"},
                    {name:"like",text:"猜你喜欢"},
                    {name:"close",text:"关闭"},
                    {name:"coupon",text:"优惠券"},
                    {name:"order",text:"订单"},
                    {name:"appraise",text:"评价"},
                    {name:"payment",text:"代付款"},
                    {name:"address",text:"地址"},
                    {name:"browse",text:"浏览"},
                    {name:"search",text:"搜索"},
                    {name:"message",text:"消息"},
                    {name:"classify",text:"分类"},
                    {name:"scanqr",text:"扫码"},
                    {name:"toparrows",text:"上箭头"},
                    {name:"btoomarrow",text:"下箭头"},
                    {name:"fullscreen",text:"全屏"},
                    {name:"paly",text:"播放"},
                    {name:"calendar",text:"日历"},
                    {name:"share",text:"分享"},
                    {name:"redpacket",text:"红包"},
                    {name:"time",text:"时间"},
                    {name:"refundMoney",text:"退款"},
                    {name:"location",text:"定位"},
                    {name:"collect",text:"收藏"},
                    {name:"phone",text:"电话"},
                    {name:"chat",text:"聊天"},
                    {name:"homepage",text:"首页"},
                    {name:"homepageSelect",text:"首页选中"},
                    {name:"setting",text:"设置"},
                    {name:"shoppingCar",text:"购物车"},
                ],
            }
        },


        components:{
            "icon-text":require("../../../../framework/component/base/wxc-icon/index.vue"),
        },

        methods:{
            onClickSelectImg(){
              console.log("111111111111111111111111111")
              if(this.isSelectShow){
                  this.isSelectShow = false;
              }else{
                  this.isSelectShow = true;
              }
            },

            onSelectCellClick(index){
                this.name = this.nameItem[index].name;
                console.log("index===============" + index)
            },
        },
    }



</script>


<style>


    .cTextTitle{
        font-size: 50px;
        color: #000000;
    }

    .cIconCenterDiv{
        margin-top: 150px;
        width: 750px;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items:center;
    }

    .cSelectDiv{
        margin-top: 50px;
        width: 400px;
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        border-color: #000000;
        border-style: solid;
        border-width: 1px;
    }

    .cSelectText{
        width: 320px;
        lines:1;
        overflow: hidden;
        text-overflow: ellipsis;
        font-size: 50px;
        color: #000000;
    }

    .cImg{
        width: 60px;
        height: 60px;
        background-color: red;
    }

    .cSelectFrameDiv{
        width: 400px;
        height: 500px;
        display: flex;
        flex-direction: column;
        border-color: #000000;
        border-style: solid;
        border-width: 1px;

    }

    .cSelectCellDiv{
        width: 400px;
        height: 80px;
        display: flex;
        flex-direction: row;
        align-items: center;
        justify-content: space-between;
        border-bottom-color: #000000;
        border-bottom-style: solid;
        border-bottom-width: 1px;
        padding: 15px;
    }

    .cCellEnglish{
        font-size: 30px;
        color: #000000;
    }
</style>