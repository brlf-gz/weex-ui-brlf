<template>
  <scroller>
    <text>垂直布局内不能够在添加垂直的滚动</text>
    <text>水平scroller</text>
    <scroller class="scroller-h" 
      append="tree" 
      scroll-direction="horizontal"
      offset-accuracy="10" 
      show-scrollbar=false
      @scroll="scrollHandler">
      <image class="image" src="https://gw.alicdn.com/tps/TB1dzanMVXXXXXQXVXXXXXXXXXX-573-412.png"></image>
      <image class="image" src="https://gw.alicdn.com/tps/TB1p9CCMVXXXXa_XFXXXXXXXXXX-450-340.png"></image>
      <image class="image" src="https://gw.alicdn.com/tps/TB1zpSiMVXXXXchXFXXXXXXXXXX-448-338.png"></image>
      <image class="image" src="https://gw.alicdn.com/tps/TB1EuGIMVXXXXcoXpXXXXXXXXXX-452-337.png"></image>
    </scroller>
    <text class = "hint">{{hint}}</text>
  </scroller>
</template>

<script>
  const dom = weex.requireModule('dom')

  export default  {
    data() {
        return{
            eventCnt: 0,
            hint:"",
            rows: []
        }
    },
    created () {
      for (let i = 0; i < 30; i++) {
        this.rows.push('row ' + i)
      }
    },
    methods: {
      scrollHandler: function(e) {
        var nowCnt = this.eventCnt + 1;
        this.eventCnt = nowCnt;
        this.offsetX = e.contentOffset.x;
        this.offsetY = e.contentOffset.y;
        this.hint = "scroll event count:" + this.eventCnt + " offsetX:" + this.offsetX + " offsetY:" +this.offsetY;
      },
    }
  };
</script>

<style scoped>
  .body {
    background-color: #ffffff;
  }
  .image {
    width:600px;
    background-color:#FFFFDF;
    height:400px;
  }
  .scroller-h {
    width: 750px;
    height:400px;
    display: flex;
    flex-direction: row;
  }

  .hint {
    width: 750px;
    height: 150px;
  }
</style>