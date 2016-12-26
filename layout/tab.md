# Tab 选项卡

## Props

### tab

| 参数         | 说明                  | 类型        | 默认值 |
| ----------- | ---------------------- | ---------- | ------- |
| line-width | 可选，边框大小 | Number | 3 |
| active-color | 可选，高亮文字的颜色和线条颜色 | String | #04be02 |
| default-color | 可选，默认文字的颜色 | String | #666 |
| animate | 可选，是否使用动画 | Boolean | true |
| index| 可选，选中tab的index | Number | 0 |
| v-model | index的双向绑定，不要和index一起用 | Number | 0 |




### tab-item

| 参数         | 说明                  | 类型        | 默认值 |
| ----------- | ---------------------- | ---------- | ------- |
| selected | 是否高亮 | Boolean | false |

## Events

| 名字 | 参数  | 描述 |
| ---- | ----- | --------------------- |
| on-index-change| index | tab选中 |




### Demo

``` vux height=50 components=Tab,TabItem
<template>
<tab>
  <tab-item :selected="demo1 === '已发货'" @click="demo1 = '已发货'">已发货</tab-item>
  <tab-item :selected="demo1 === '未发货'" @click="demo1 = '未发货'">未发货</tab-item>
  <tab-item :selected="demo1 === '全部订单'" @click="demo1 = '全部订单'">全部订单</tab-item>
</tab>
</template>

<script>
export default {
  data () {
    return {
      demo1: '未发货'
    }
  }
}
</script>
```

### 更简洁的粟子

``` vux height=50 components=Tab,TabItem

<template>
<tab :line-width="2" active-color="#fc378c">
  <tab-item :selected="demo2 === item" v-for="item in list2" @click="demo2 = item"><<item>></tab-item>
</tab>
</template>

<script>
export default {
  data () {
    return {
      demo2: '美食',
      list2: ['精选', '美食', '电影', '酒店', '外卖']
    }
  }
}
</script>

```

### 禁用滑动动画

``` vux height=50 components=Tab,TabItem
<template>
<tab :line-width="1" :animate="false">
  <tab-item :selected="demo2 === item" v-for="item in list2" @click="demo2 = item"><<item>></tab-item>
</tab>
</template>

<script>
export default {
  data () {
    return {
      demo2: '美食',
      list2: ['精选', '美食', '电影', '酒店', '外卖']
    }
  }
}
</script>
```

> 更多的demo请手机访问 `http://jh-wong.com/vux2` 进行查看。

+ [tab](http://jh-wong.com/vux2/#/component/tab)


