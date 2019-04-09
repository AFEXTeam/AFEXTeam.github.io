# ab-manager-focus@焦点管理

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
this.focusManager.toggleFocus();
```

4.切换交易签页时，重置会上次离开是的焦点位置（也可以使用下面的方法）：

```js
this.focusManager.toggleFocus();
```

5.手动设置焦点位置

```js
this.focusManager.setFocus(ref);
```

例：
```js
<template>
    <aui-input ref="accountInput"></aui-input>
</template>
<script>
    this.focusManager.setFocus("accountInput");
</script>
```

6.设置/移除焦点贪婪

```js
this.focusManager.setGreedy(refNames[, scope]);
this.focusManager.removeGreedy(refNames[, scope]);
```


```html
<template>
    <aui-input ref="input_1" v-model="inputValue"></aui-input>
</template>
<script>
    import { FocusManager } from 'ab-manager-focus'

    export default {
        data() {
            return {
                focusManager: ''
            }
        },
        mounted() {
            this.focusManager.setGreedy('input_1');
            this.focusManager.removeGreedy('input_1');
        }
    }
</script>
```

| 参数     | 类型 | 默认值 | 说明 |
| -------- | --- | --- | --- |
| this | object(VueComponent) | this | 当前作用域 |
| ref | string/number | - | 声明在组件上的ref属性或组件的位置下标 |
| refNames | string/array | - | 一个ref字符串或者多个ref字符串组成的数组 |
| scope | object(VueComponent) | this | attach方法传入的作用域 |
