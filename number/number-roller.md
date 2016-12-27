# number-roller

## 属性

| 参数         | 说明                  | 类型        | 默认值 |
| ----------- | ---------------------- | ---------- | ------- |
| number | 可选(异步赋值)，选项值 | Number | 0 |
| width | 必选，数字位数 | Number | -- |

## demo

``` html
<template>
<number-roller :number="number" :width="6"></number-roller>
</template>

<script>
export default {
  mounted() {
    setInterval(() => {
      this.number = 100000 + Math.round(Math.random() * 899999)
    }, 3000)
  },
  data () {
    return {
      number: 123765
    }
  }
}
</script>
```