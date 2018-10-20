# ab-manager-focus

交易页面焦点控制器，实现交易全键盘操作。

> 通常与`ab-ui-validator-manager-vue`配合使用，用来提示错误信息。

1.引入

```js
import { FocusManager } from "ab-manager-focus";
```

2.初始化焦点逻辑：

```js
this.focusManager = new FocusManager();

this.focusManager.attach(this);
```

3.触发了页面布局改变后(包括DOM元素的增、删、禁用)，重置`FocusManager`：

```js
this.focusManager.toggle();
```

4.切换交易签页时，重置上次离开是的焦点位置：

```js
this.focusManager.toggle();
```

| 参数     | 类型 | 说明 |
| -------- | --- | --- |
| this | object(Vue实例) | 当前作用域 |