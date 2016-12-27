# datetime 时间

> 需要与`group`一起使用。

## Props

| 名字 | 类型 | 默认 | 描述 |
|-----|-----|-----|-----|
| format | String | 'YYYY-MM-DD' | 显示格式 |
| title | String | 无 | 显示标题 |
| value | String | 默认为当前日期 | 日期值 |
| v-model | String | 默认为当前日期 | value的双向绑定 |
| inline-desc | String | 无 | 副标题 |
| placeholder | String | 无 | 提示文字 |
| min-year | Number | 无 | 最小可选年 |
| max-year | Number | 无 | 最大可选年 |
| confirm-text | String | ok | 确认按钮文字 |
| cancel-text | String | cancel | 取消按钮文字 |
| year-row | String | {value} |年份显示格式 |
| month-row | String | {value} | 月份显示格式 |
| day-row | String | {value} | 日期显示格式 |
| hour-row | String | {value} | 小时显示格式 |
| minute-row | String | {value} | 分钟显示格式 |

## demos

``` html
<template>
  <div>
    <group title="default format: YYYY-MM-DD">
      <datetime v-model="value1" @on-change="change" title="Birthday"></datetime>
    </group>

    <group title="YYYY-MM-DD HH:mm">
      <datetime v-model="value2" format="YYYY-MM-DD HH:mm" @on-change="change" title="start time" inline-desc="select hour and minute"></datetime>
    </group>

    <group title="Placeholder">
      <datetime v-model="value3" format="YYYY-MM-DD" placeholder="Please select" @on-change="change" title="start time"></datetime>
    </group>

    <group title="specified min-year and max-year">
      <datetime v-model="value4" placeholder="Please select" :min-year=2000 :max-year=2016 format="YYYY-MM-DD HH:mm" @on-change="change" title="years after 2000"></datetime>
    </group>

    <group title="specified template text in Chinese">
      <datetime v-model="value5" placeholder="请选择日期" :min-year=2000 :max-year=2016 format="YYYY-MM-DD HH:mm" @on-change="change" title="Chinese" year-row="{value}年" month-row="{value}月" day-row="{value}日" hour-row="{value}点" minute-row="{value}分" confirm-text="完成" cancel-text="取消"></datetime>
    </group>

    <group title="show center button and clear the value">
      <datetime v-model="value6" @on-change="change" title="Birthday" clear-text="clear" @on-clear="clearValue"></datetime>
    </group>

    <group title="show center button to set date to today">
      <datetime v-model="value7" @on-change="change" title="Birthday" clear-text="today" @on-clear="setToday"></datetime>
    </group>

  </div>
</template>

<script>
import  Datetime from 'vuxx/src/components/Datetime'
import  Group  from 'vuxx/src/components/Group'

export default {
  components: {
    Datetime,
    Group
  },
  data () {
    return {
      value1: '2016-02-11',
      value2: '',
      value3: '',
      value4: '',
      value5: '',
      value6: '2016-08-18',
      value7: ''
    }
  },
  methods: {
    change (value) {
      console.log('change', value)
    },
    clearValue (value) {
      this.$data.value6 = ''
      console.log('clear')
    },
    setToday (value) {
      let now = new Date()
      let cmonth = now.getMonth() + 1
      let day = now.getDate()
      if (cmonth < 10) cmonth = '0' + cmonth
      this.$data.value7 = now.getFullYear() + '-' + cmonth + '-' + day
      console.log('set today ok')
    }
  }
}
</script>

```
