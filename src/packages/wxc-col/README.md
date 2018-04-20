# wxc-col
## 控件说明
封装`<div/>`的flex-direction: column

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
       <wxc-col>
           <text>1</text>
           <text>2</text>
           <text>3</text>
       </wxc-col>
        <wxc-col>
            <text>1</text>
            <text>2</text>
            <text>3</text>
        </wxc-col>
        <wxc-col>
            <text>1</text>
            <text>2</text>
            <text>3</text>
        </wxc-col>
    </div>
</template>

<script>
    import {WxcCol} from '../../../../packages/component/index'

    export default {

        components: {
            'wxc-col': WxcCol,
        },
        
    }
</script>

```

## 注意事项：
无


