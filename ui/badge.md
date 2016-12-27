# badge

## Props

| 名字 | 类型 | 默认 | 描述 |
|-----|-----|-----|-----|
| text | String | 无 | 文字 |

## Demo

``` html

<template>
<div>
  <badge text="1"></badge>
  <br>
  <badge text="123"></badge>
  <br>
  <group>
    <cell title="Used in a Cell">
      <div class="badge-value">
        New Message &nbsp;
        <badge text="8"></badge>
      </div>
    </cell>
  </group>
</div>
</template>
```