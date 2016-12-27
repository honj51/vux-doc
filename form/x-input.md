# x-input 单行文本输入

> 命名为`x-input`避免与原生`input`标签渲染冲突

> 注意不要混淆：`x-input`不是原生`input`,不支持大多数`input`上的事件如`focus`等，如果实在需要处理input事件，可以直接参照WeUI文档直接用html标签。

> `x-input`需要与`group`配合使用


## Props

| 名字 | 类型 | 默认 | 描述 |
|-----|-----|-----|-----|
| title | String | 无 | 标题 |
| value | String | 无 | 表单值,不支持双向绑定,双向绑定请用v-model |
| v-model|String | 无 | value值的双向绑定,不要混用 |
| inline-desc | String | 无 | 标题下文字 |
| keyboard | String | 无 | 只支持 `number`,用于激活数字键盘 |
| placeholder | String | 无 | 输入提示 |
| show-clear | Boolean | true | 是否显示清除按钮 |
| type | String | text | 设置组件内input的type |
| is-type | String | 无 | 内置验证类型，支持`email`,`china-mobile`,`china-name` | 
| readonly | Boolean | false | 只读，不要修改 |
| min | Number | 无 | 最小字符数 |
| max | Number | 无 | 最大字符数 |
| equal-with | String | 无 | 当前input需要与某input输入完全一致，用于确认填写 |
| text-align | String | left | input的对齐样式 |

## Events


| 名字 | 参数  | 描述 |
|-----|-----|-----|
| on-change | (value) | 当值改变时触发 |


## Demos

``` html
<!-- 必须输入6-10位的电子邮件地址 -->
<x-input :min=6 :max=10 is-type=email v-model="value"></x-input>
<!-- 手机号码验证 -->
<x-input 
    title="手机号"
    is-type="china-mobile" 
    :show-clear=true 
    placeholder="请输入手机号"></x-input>
<!-- 必须输入123456 -->
<group title="等值判断">
  <x-input title="请输入6位数字" type="text" placeholder="" v-model="password" :min="6" :max="6" @on-change="change"></x-input>
  <x-input title="请确认6位数字" type="text" placeholder="" :equal-with="password"></x-input>
</group>
```
