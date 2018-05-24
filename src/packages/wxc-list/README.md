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
参考[示例](https://github.com/brlf-gz/weex-ui-brlf/blob/master/src/demo/wxc-list/index.vue).

## 注意事项：
* web端底层用`<scroller/>`封装，ios/android端用<list/>`<list/>`封装
* 属性refresh与refreshDisplay必须成对使用



