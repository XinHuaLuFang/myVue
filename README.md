# myVue

* 只有被Vue代理的属性是响应的，在实例创建之后添加新的属性到实例上，新属性不会触发视图更新。
* 不要在实例属性或者回调函数中（如 vm.$watch('a', newVal => this.myMethod() ）使用`箭头函数`。因为剪箭头函数绑定父上下文，所以 `this` 不会像预想的一样是 Vue 实例，而是 `this.myMethod` 未被定义。
* 钩子 `created` `mounted` `updated` `destroyed`，钩子的 `this` 指向调用它的 Vue 实例。Vue没有“控制器”的概念。组件的自定义逻辑可以分布在这些钩子中。