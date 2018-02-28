# wxc-touch-div
## 控件说明
封装了对div的点击添加点击效果

## 属性
* color： 指定当前div默认的颜色为白色
* touchColor：当前div点击时的颜色，默认是‘#ffff00’


## 方法
无

## 事件
* onClick：点击事件


## 用法：

```vue
<wxc-touch-div class="cTouchDiv"
        color="#ff0000"
        @onClick="onClick('one')"
        touch-color="#ff8800">
    <text class="cText">Click Me</text>
</wxc-touch-div>
```

## 注意事项：
无


