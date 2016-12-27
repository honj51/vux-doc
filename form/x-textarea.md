# x-textarea 多行文本输入框

> 需要与`group`搭配使用

## Props

| 参数         | 说明          | 类型       | 默认值     | 
| -------     | ------------- | ------     | --------- | 
| required    | 是否必填       | Boolean    | true      |
| show-counter | 是否显示字数统计（需要设置max） | Boolean  | | 
| max         | 最大字符数，超出字符数 | Number |        | 
| value       | 值字段   | String     | 无       | 
| v-model       | value的双向绑定   | String     | 无       |
| placeholder | placeholder   | String     | 无        | 
| rows | 行数 | Number | 3 | 
| cols | 列数 | 30 | Number | 
| height | 高度 | Number | 无 | 

## Demo
* 普通的多行输入框

```html

<template>
  <group title="textarea">
    <x-textarea :max="200" placeholder="请输入详细描述"></x-textarea>
  </group>
</template>

```


* 不显示字数统计

```html

<template>
  <group title="不显示字符统计">
    <x-textarea :max="200" placeholder="请输入详细描述" :show-counter="false"></x-textarea>
  </group>
</template>
```
