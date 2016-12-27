# Alert

## Props

| 参数         | 说明                  | 类型        | 默认值 |
| ----------- | ---------------------- | ---------- | ------- |
| button-text | 可选，按钮文字 | String | OK |
| 默认slot | 可选，提示消息内容 | DOM | 无 |
| title | 必选，提示标题 | String | 无 |
| show | 必选，是否显示 | Boolean | false |
|v-model | show`双向绑定` | Boolean | false |
| on-show | 显示时事件 | 事件 | 无 |
| on-hide | 关闭时事件 | 事件 | 无 |


## Demo

### 默认按钮文字

``` 
<template>
<group>
  <switch title="Toggle" :value.sync="show"></switch>
</group>
<alert :show.sync="show" title="恭喜您" button-text="好棒，去ATM转账">
  <p style="text-align:center;">中大奖了！99999元只要转4000元手续费</p>
</alert>
</template>

<script>
export default {
  data () {
    return {
      show: true
    }
  }
}
</script>
```