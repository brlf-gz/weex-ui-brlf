# wxc-row
## 控件说明
封装`<div/>`的flex-direction: row

## 属性
无

## 方法
无

## 事件
无

## 用法：

```vue
<template>
    <div>
       <wxc-row>
           <text>1</text>
           <text>2</text>
           <text>3</text>
       </wxc-row>
        <wxc-row>
            <text>1</text>
            <text>2</text>
            <text>3</text>
        </wxc-row>
        <wxc-row>
            <text>1</text>
            <text>2</text>
            <text>3</text>
        </wxc-row>
    </div>
</template>

<script>
    import {WxcRow} from '../../../../packages/component/index'

    export default {

        components: {
            'wxc-row': WxcRow,
        },
        
    }
</script>

```

## 注意事项：
无


