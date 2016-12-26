# Scroller

> Scroller 依赖于[`xscroll`](https://github.com/huxiaoqi567/xscroll)

## Props

| 名字 | 类型 | 默认 | 描述 |
|-----|-----|-----|-----|
| height | String | Viewport高度 | 高度 |
| lockX | Boolean | false | 锁定X方向 |
| lockY | Boolean | false | 锁定Y方向 |
| scrollbarX | Boolean | false | 横向滚动条 |
| scrollbarY | Boolean | false | 垂直方向滚动条 |
| bounce | Boolean | true | 是否有边缘回弹 |
| use-pulldown| Boolean | false | 是否使用下拉组件 |
| use-pullup | Boolean | false | 是否使用上拉组件 |
| pulldown-config | Object | 见下面 | 下拉组件配置 |
| pullup-config| Object | 见下面 | 上拉组件配置 |
| pulldown-status | String | 无 | 双向绑定，当需要自定义下拉刷新行为时配置 |
| pullup-status | String | 无 | 双向绑定，当需要自定义上拉行为时配置 |

pulldown-config默认：

``` json
{
  content: 'Pull Down To Refresh',
  height: 60,
  autoRefresh: false,
  downContent: 'Pull Down To Refresh',
  upContent: 'Release To Refresh',
  loadingContent: 'Loading...',
  clsPrefix: 'xs-plugin-pulldown-'
}
```

pullup-config默认

``` json
{
  content: 'Pull Up To Refresh',
  pullUpHeight: 60,
  height: 40,
  autoRefresh: false,
  downContent: 'Release To Refresh',
  upContent: 'Pull Up To Refresh',
  loadingContent: 'Loading...',
  clsPrefix: 'xs-plugin-pullup-'
}
```

## Methods

| 名字 | 参数 | 描述  |
|-----|-----|-----|
| reset | 无 | 重新渲染，因为scroller并不知道内部内容是否变化，因此需要手动取得`ref`进行reset, 并且需要在`$nextTick`中执行。

示例：

``` javascript
this.$nextTick(() => {
  this.$refs.scroller.reset()
})
```

## Events

| 名字 | 参数  | 描述 |
|-----|-----|-----|
| pullup:loading| (that)scroller的实例 | 上拉加载时触发的事件，需要在获取数据后使用`$emit`触发状态更新， `that.$emit('pullup:reset', that.uuid)` |
| pulldown:loading| (that)scroller的实例 | 下拉加载时触发的事件，需要在获取数据后使用`$emit`触发状态更新， `that.$emit('pulldown:reset', that.uuid)` |
| pullup:disable | (scroller的uuid) | 禁用上拉加载，当没有更多数据需要禁用时使用`$emit`和`ref`方式结合触发禁用，需要设置ref，` this.$refs.scroller.$emit('pullup:disable',this.$refs.scroller.uuid)` |
| pullup:enable | (scroller的uuid) | 启用上拉加载，禁用插件后，当又重新需要时使用`$emit`和`ref`方式结合触发禁用，需要设置ref，`this.$refs.scroller.$emit('pullup:enable',this.$refs.scroller.uuid)`` |



## Slots

> 注意，默认slot根元素必须有且只有一个, 如`<scroller><div>content</div></scroller>`

| 名字  | 描述 |
|-----|-----|
| 默认slot | 无 |



## Demos

> 更多的demo请手机访问 `http://jh-wong.com/vux2` 进行查看。

+ [scroller](http://jh-wong.com/vux2/#/component/scroller)
+ [pullup](http://jh-wong.com/vux2/#!/component/pullup)
+ [pulldown](http://jh-wong.com/vux2/#!/component/pulldown)
+ [pulldown & pullup](http://jh-wong.com/vux2/#!/component/pulldown-pullup)

``` html
<scroller lock-y :scrollbar-x="false">
  <div class="box1">
    many many content
  </div>
</scroller>
```
