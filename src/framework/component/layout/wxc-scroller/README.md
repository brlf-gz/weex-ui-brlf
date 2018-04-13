# wxc-scroller(web)
## 控件说明
封装`<scroller/>`的加载更多

## 属性
| Prop | Type | Default | Description |
| --- | --- | --- | --- |
| loadmore | Function | null| 接收加载更多事件 |


## 方法
无

## 事件
无


## 用法：

```vue
<template>
    <div>
        <wxc-scroller :loadmore="onloadmore">
            <text v-for="item in list">{{item}}</text>
        </wxc-scroller>
    </div>
</template>

<script>
    import {WxcScroller} from '../../../../framework/component/index'

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
            "wxc-scroller": WxcScroller,
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
```

## 注意事项：
* 只适用于web端


