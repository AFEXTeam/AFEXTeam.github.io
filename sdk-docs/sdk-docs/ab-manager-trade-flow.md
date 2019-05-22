# ab-manager-trade-flow@流程管理

页面流程管理器，在动态组件中控制当前加载的页面以及记录交易日志。

> 通常与ab-manager-pages配合使用。

1.引入

```js
import { TradeFlowManager } from "ab-manager-trade-flow";
```

2.打开vue页面：

```js
TradeFlowManager.run(name, scope);
```

例：

```js
TradeFlowManager.run('Step1', this);
```

3.记录交易日志

```js
// main.js
import { TradeFlowManager } from "ab-manager-trade-flow";
Vue.use(TradeFlowManager[,options]);
```

> 在每个交易的`main.js`引用一次即可，会记录交易中的“点击”、“focus”和“blur”等事件触发的相关信息。

| 参数     | 类型 | 说明 |
| -------- | --- | --- |
| name | string | 打开页面的名字(与ab-manager-pages中的stepName对应) |
| scope | object(Vue实例) | 页面宿主(动态组件所在的Vue实例，通常为this) |
| options.callback | function | 事件埋点的回调，默认一个信息参数 |