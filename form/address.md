# Address

> XAddress 依赖于`Popup`, `Picker`, `Cell`

## Props

| 名字 | 类型 | 默认 | 描述 |
|-----|-----|-----|-----|
| title | String | 无 | 标题 |
| value | Array | [] | 表单值，`双向绑定` |
| list | Array | 无 | 地址库, address源码目录下有`list.json` |
| inline-desc | String | 无 | cell的子标题 |

## Events
| 名字 | 参数 | 说明 |
|-----|-----|-----|
| on-hide | closeType(布尔值:true表示选择完成,false表示取消) , value(选择的值) |此处包括on-ok,根据closeType判断 |
| on-ok| val | 选择完成事件 |
| on-cancel | 无| 取消 |
| on-show| 无 | show |



## Demos

``` html
<template>
  <div>
    <group>
      <x-address :title="title" :value="value" :list="addressData"></x-address>
      <cell title="上面value值" :value="value.join('')"></cell>
      <x-address :title="title2" :value="value2" raw-value :list="addressData"></x-address>
      <x-address title="二级省市" :value="value3" raw-value :list="addressData"></x-address>
    </group>
    <br/>
    <x-button type="primary" @click="changeData">改变数据</x-button>
  </div>
</template>

<script>
import { Group, XAddress, AddressChinaData, XButton, Cell } from '../components'

export default {
  components: {
    Group,
    XAddress,
    XButton,
    Cell
  },
  data () {
    return {
      title: '默认为北京',
      value: [],
      title2: '手动设定',
      value2: ['广东省', '深圳市', '南山区'],
      value3: ['海南省', '儋州市', '--'],
      addressData: AddressChinaData
    }
  },
  methods: {
    changeData () {
      this.value2 = ['430000', '430400', '430407']
    }
  }
}
</script>
```