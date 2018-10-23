# ab-manager-sync-flow@同步交易管理

支持交易同步打开，包括但不限于在dialog弹出时，阻止后续逻辑执行，在完成dialog是才执行。

1.引入

```js
import { SyncFlowManager } from "ab-manager-sync-flow"
```

2.订阅接下来的操作：

```js
SyncFlowManager.block(topic, continueFunction);
```

> 将要在dialog等处理之后执行的逻辑放在`continueFunction`中。

3.在想要触发订阅函数的位置发布：

```js
SyncFlowManager.continue(topic, args);
```

4.清除某个订阅的操作：

```js
SyncFlowManager.cancel(topic);
```

5.清除所有订阅的操作：

```js
SyncFlowManager.cancelAll();
```

| 参数     | 类型 | 说明 |
| -------- | --- | --- |
| topic | string | 识别的唯一token,识别对应的方法 |
| continueFunction | function | 具体操作 |
| args(可选) | - | 参数 |