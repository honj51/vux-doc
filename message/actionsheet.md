# Actionsheet

## Props

| 参数        | 类型        | 默认值 | 说明 |
| ----------- | ---------------------- | ---------- | ------- |
| show | Boolean | false | 显示绑定值|
| v-model | Boolean | false |show   `双向绑定` |
| show-cancel | Boolean | false | 是否显示取消按钮 |
| menus  | Object | {} |  菜单列表，格式见下|
| cancelText | String | cancel | 取消按钮文字 |

> menus格式如下

``` js
{
  menu1: 'Take Photo',
  menu2: 'Choose from photos'
}
```

## Events

| 事件名       | 参数       | 说明 |
| ----------- | ---------------------- | ---------- |
| on-menu-click | (menuKey, menuValue) | 点击菜单时触发 |
| on-cancel | -- | 点击取消时触发 |


## Demo

``` html
<template>
<div>
  <group>
    <x-switch title="show actionsheet1" v-model="show1"></x-switch >
    <x-switch title="show actionsheet2" v-model="show2"></x-switch >
    <x-switch title="show actionsheet3" v-model="show3"></x-switch >
  </group>
  <actionsheet v-model="show1" :menus="menus1"></actionsheet>
  <!-- 显示取消按钮 -->
  <actionsheet v-model="show2" :menus="menus2" show-cancel></actionsheet>
  <!-- 菜单响应 -->
  <actionsheet v-model="show3" :menus="menus3" @on-click-menu="click" show-cancel @cancel-text="取消"></actionsheet>
</div>
</template>

<script>
export default {
  data () {
    return {
      show1:false,
      menus1:{
        menu1: 'Share to friends',
        menu2: 'Share to timeline'
      },
      show2:false,
      menus2: {
        menu1: 'Take Photo',
        menu2: 'Choose from photos'
      },
      show3:false,
      menus3: {
        menu1: 'friends comment'
      }
    }
  },
  methods: {
    click (key) {
      console.log(key)
    }
  }
}
</script>
```
