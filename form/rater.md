# Rater 评分组件

## Props

| 参数         | 说明                  | 类型        | 默认值 |
| ----------- | ---------------------- | ---------- | ------- |
|max|可选，最高评分值|Number|5|
|value|可选，评分值|Number|0|
| v-model | Boolean | false | value的双向绑定 |
|disabled|Boolean|可选，不可点击|false|
|star|可选，评分图标样式|String|★|
|active-color|可选，激活颜色|String|#fc6|
|margin|可选，图标间距离|Number|2|
|fontSize|可选，图标大小|Number|25|


### 一般使用

``` 
<template>
<div>
    <rater :value=3></rater>
</div>
<div>
    <rater :value=2 :margin="15" active-color="#04BE02"></rater>
</div>
<div>
    <rater :value=5 :max=6 :font-size=15 active-color="#FF9900"></rater>
</div>
</template>
<style>
div {
    margin:5px 0;
}
</style>
```

### 不可点击

``` 
<template>
<div>
    <rater :value=4 disabled></rater>
</div>
<div>
    <rater :value=3.5  active-color="#04BE02" disabled></rater>
</div>
</template>
<style>
div {
    margin:5px 0;
}
</style>
```

### 自定义评分图标

``` 
<template>
<div>
    <rater :value="5" star="☼" active-color="#FF9900"></rater>
</div>
<div>
    <rater :value="4" star="囧" active-color="#FF9900"></rater>
</div>
</template>
<style>
div {
    margin:5px 0;
}
</style>
```

### 双向绑定

``` 
<template>
<rater v-model="rate"></rater>
<div v-text="'评分:' + rate"></div>
</template>
<script>
export default {
    data: {
        rate:3
    }
}
</script>
```
