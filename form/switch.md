# Switch

> 作为行内表单组件，`XSwitch`必须和`Group`一起使用。

## Props

| 名字 | 类型 | 默认 | 描述 |
|-----|-----|-----|-----|
| value | Boolean | false | 表单值 |
| v-model | Boolean | false | value的双向绑定 |
| title | String | 无 | cell标题 |
| disabled | Boolean | false | 是否禁止操作 |
| inline-desc| String | 无 | 副标题 |


## Events


| 名字 | 参数  | 描述 |
|-----|-----|-----|
| on-change| (value) | 值变化时触发 |


## 直接值

``` html

<template>
<group>
  <x-switch title="Switch" :value="true"></x-switch>
  <x-switch title="Switch" :value="false"></x-switch>
</group>
</template>
```

## 双向绑定

``` html

<template>
<group>
  <x-switch :title="'双向绑定:值为' + value1" v-model="value1"></x-switch>
  <x-switch :title="'双向绑定:值为' + value1" v-model="value1"></x-switch>
</group>
</template>

<script>
export default {
  data: {
    value1: true
  }
}
</script>
```

### disabled 设置不可更改

``` html

<components>
XSwitch,Group
</components>
<template>
<group>
  <x-switch title="不可更改" :value="true" disabled></x-switch>
  <x-switch title="不可更改" :value="false" disabled></x-switch>
</group>
</template>
```

### title支持html

``` html

<template>
<group>
  <x-switch title="<span style='color:red'>红色文字</span>" :value="true"></x-switch>
</group>
</template>
```

### on-change 事件

``` html

<template>
<group>
  <x-switch title="监听事件" :value="true" @on-change="change"></x-switch>
</group>
</template>
<script>
export default {
  methods: {
    change: function (val) {
      console.log('change', val)
    }
  }
}
</script>
```

