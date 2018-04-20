# wxc-progress
## 控件说明
进度条封装

## 属性
| Prop | Type  | Default | Description |
|:----:|:---:|:-------:|:----------:|
|percent|Number|0|进度百分比|
|barWidth|Number|600|进度条宽度|
|barHeight|Number|100|进度条高度|
|bgColor|String|#ebebeb|进度条背景颜色|
|activeColor|String|#0eadff|已下载进度颜色|
|textColor|String|#000000|下载进度文字颜色|
|showInfo|Boolean|false|是否显示下载进度文字|


## 方法
无

## 事件
无


## 用法：

```vue
<wxc-progress class="progress"
                      :percent=percent
                      :bar-width=barWidth
                      :bar-height=barHeight
                      :bg-color=bgColor
                      :active-color=activeColor
                      :text-color=textColor
                      :show-info=showInfo>
</wxc-progress>
```

## 注意事项：
无


