# wxc-list
## 控件说明
封装长列表组件

## 属性
| Prop | Type | Default | Description |
| --- | --- | --- | --- |
| refresh | Function | null| 接收下拉刷新事件 |
| refreshDisplay | Boolean | false| 控制`<refresh/>`|
| loadmore | Function | null| 接收加载更多事件 |

## 方法
无

## 事件
无

## 用法：

```vue
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

    import {WxcList} from "../../packages/index";

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
```

## 注意事项：
* web端底层用`<scroller/>`封装，ios/android端用<list/>`<list/>`封装
* 属性refresh与refreshDisplay必须成对使用



