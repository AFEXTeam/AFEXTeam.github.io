# ab-manager-hotkeys

js绑定热键组合，方便操作，提升效率

1.引入

```js
import { HotKeys } from "ab-manager-hotkeys";
```

2.绑定快捷键

```js
HotKeys.createHotKeys(shortcut, callback);
```

3.解除快捷键绑定

```js
HotKeys.unbind(shortcut);
```

例：
```js
<script>
    methods: {
        /* 热键回调函数
        *
        * hotKeyFun(e, handler)其中参数无需修改
        * e: 当前点击的event
        * handler: 包括组合键的信息
        */
        hotKeyFun(e, handler) {
            e.preventDefault();
            switch (handler.key) {
                case "alt+1":
                    console.log("按了" + handler.key); // "按了alt+1"
                break;
                case "alt+2":
                    console.log("按了" + handler.key); // "按了alt+2"
                break;
            }
        }
    },
    mounted() {
        // 绑定
        HotKeys.createHotKeys('alt+1,alt+2', this.hotKeyFun);

        // 解绑
        HotKeys.unbind('alt+1');
    }
</script>
```
4.按区域绑定热键

```js
HotKeys.createHotKeys(shortcut, scope, callback);

HotKeys.setScope(scope); // 默认为所有
```

5.解绑某个区域中的所有热键

```js
HotKeys.deleteScope(scope);
```

例：

```js
HotKeys.createHotKeys('alt+1', 'scope1', function(e, handler){
    console.log('在scope1中按下了alt+1');
});

HotKeys.setScope('scope1');
// 解绑
// HotKeys.deleteScope('scope1');
```

6.过滤节点

> 默认`INPUT`、`SELECT`、`TEXTAREA`默认不做处理；如果想要在这些元素中生效，需要设置`HotKeys.filter`返回`true`。

```js
HotKeys.filter(function(event){
  return true;
});
```

| 参数     | 类型 | 说明 |
| -------- | --- | --- |
| shortcut | string | 快捷键组合 |
| scope(可选) | string | 指定热键绑定的区域 |
| callback | function | 快捷键绑定的函数 |