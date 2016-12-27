# Popup弹出层

## Props

| 参数         | 说明                  | 类型        | 默认值 |
| ----------- | ---------------------- | ---------- | ------- |
| show | 是否显示Popup | Boolean | false |
| height | 弹出层高度 | String | auto |
| v-model | show的双向绑定 | Boolean | false |

> 如果希望弹出层铺满整个屏幕，则可设置`height=100%`

## Events

| 名字 | 参数  | 描述 |
|-----|-----|-----|
| on-first-show | - | 第一次出现时，用于需要在第一次进行异步数据获取或者必要的UI渲染（如Popup内有Scroller）|

## Demo

``` html
<template>
<div>
  <group>
    <switch title="Default popup" v-model="show"></switch>
    <switch title="Full popup" v-model="show1"></switch>
  </group>
  <popup v-model="show">
    <div class="popup0">
      <group>
        <switch title="Another Switcher" v-model="show"></switch>
      </group>
    </div>
  </popup>

  <popup v-model="show1" height="100%">
    <div class="popup1">
      <group>
        <switch title="Another Switcher" v-model="show1"></switch>
      </group>
    </div>
  </popup>
</div>
</template>
<script>
export default {
	data () {
		return {
			show: false,
			show1: false
		}
	}
}
</script>
<style>
.popup0 {
  padding-bottom:15px;
  height:200px;
}
.popup1 {
  width:100%;
  height:100%;
}
</style>
```
