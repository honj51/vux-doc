# 常见问题

## 其他格式的文档有么?

+ [PDF](https://www.gitbook.com/download/pdf/book/jinhuiwong/vuxx)
+ [ePub](https://www.gitbook.com/download/epub/book/jinhuiwong/vuxx)
+ [Mobi](https://www.gitbook.com/download/mobi/book/jinhuiwong/vuxx)

## 不懂Vue， 怎么用

去学

## Vux是微信官方项目吗

不是，但是Vux依赖于微信官方开发的[`WeUI`](https://github.com/weui/weui)

## Vux和Vuex名字太像了

真不是故意的

## 可以在template中使用其他标签吗

当然可以，局部注册组件的时候指定名字。

``` js
{
  components: {
    xalert: Alert
  }
}

```

如果使用全局注册，则

``` js
Vue.component('xalert', vuxAlert)
```

## 为什么部分组件要加x-前缀

若不更名，可能在开发时与标准html标签相同而导致冲突或者bug。

## 有QQ交流群吗

537322257

