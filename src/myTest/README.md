## 01，测试 `$dispatch` 和 `$on`

`$dispatch` 是 element 实现的（vue1.0 版本中的实现，现在已经废弃。）[参考](https://juejin.im/post/5c7fd345f265da2da771f4cd)

[访问父子组件实例的方式](https://cn.vuejs.org/v2/guide/components-edge-cases.html#%E8%AE%BF%E9%97%AE%E7%88%B6%E7%BA%A7%E7%BB%84%E4%BB%B6%E5%AE%9E%E4%BE%8B)

1，`$emit` 可以被 `$on` 监听到。

2，`$dispatch` 主要是为了逐层触发父级的事件，父级会通过 `$on` 来监听。

3，`$root` 根实例，是指 `main.js` 中定义的实例。不是 `App.vue` 中的实例。

4，`$parent` 和 `$children` 都是直接的父子实例。

5，`$options`，可以获取 Vue 实例的初始化选项。

打印 `this.$options` 时，看不到下面的这些属性，是因为在 `__proto__` 上。

``` js
export default {
  name: 'ElFormItem',
  componentName: 'ElFormItem',
  customOption: 'foo',
}
```