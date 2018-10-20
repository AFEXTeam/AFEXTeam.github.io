# ab-manager-trade-flow

页面流程管理器，在动态组件中控制当前加载的页面。

> 通常与ab-ui-page-manager-vue配合使用。

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

| 参数     | 类型 | 说明 |
| -------- | --- | --- |
| name | string | 打开页面的名字(与ab-ui-page-manager-vue中的stepName对应) |
| scope | object(Vue实例) | 页面宿主(动态组件所在的Vue实例，通常为this) |