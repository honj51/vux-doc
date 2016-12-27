# selector

> 需要配合`group`使用

## Props

| 名字 | 类型 | 默认 | 描述 |
|-----|-----|-----|-----|
| title | String | 无 | 标题 |
| placeholder | String | 无 | placeholder |
| readonly | Boolean | false | 只读 |
| value | String | 无 | 表单值 |
| v-model| String | 无 | value的双向绑定 |
| options | Array | 无 | 选项，支持简单数组及key=>value键值对 |

## Events


| 名字 | 参数  | 描述 |
|-----|-----|-----|
| on-change | (value) | 值变化时触发 |

## Demos

```
<template>
<div>
  <group :title="'no placeholder, the current value is : ' + defaultValue">
    <selector title="省份" :options="list" v-model="defaultValue"></selector>
  </group>

  <group title="with placeholder">
    <selector placeholder="请选择省份" title="省份" :options="list" @on-change="onChange"></selector>
  </group>

  <group title="without title">
    <selector placeholder="请选择省份" :options="list"></selector>
  </group>

  <group title="set value=广西">
    <selector v-model="value1" title="省份" :options="plainList" @on-change="onChange"></selector>
  </group>

  <group title="readonly, displays just like a cell">
    <selector value="gd" readonly title="省份" :options="list"></selector>
  </group>

  <group title="use plain options">
    <selector value="C" title="Selector" :options="list1" @on-change="onChange"></selector>
  </group>

  <group title='multi selector'>
    <selector placeholder="请选择省份" title="省份" :options="list"></selector>
    <selector v-model="value2" title="省份" :options="list"></selector>
  </group>
</div>
</template>

<script>
export default {
  data () {
    return {
      defaultValue: '',
      plainList: ['广东', '广西'],
      list: [{key: 'gd', value: '广东'}, {key: 'gx', value: '广西'}],
      value1: '广西',
      value2: 'gd',
      list1: ['A', 'B', 'C']
    }
  },
  methods: {
    onChange (val) {
      console.log(val)
    }
  }
}
</script>
```