# ab-manager-hotkey@热键管理

用于注册及删除全局热键、交易级热键和组件热键。

### 1.引入

```js
import { Hotkey } from 'ab-manager-hotkey'
Vue.use(Hotkey);
```

### 2.注册

```js
this.$setHotkey(name, data[, scope]);
```

**注：只能使用此方法注册热键。**

#### 2.1 全局及交易级热键注册
```html
// App.vue
<template>
    <div id="app" v-hotkey="keymap"></div>
</template>
<script>
export default {
    data() {
        return {
            keymap: {}
        }
    },
    mounted() {
        this.$setHotkey('keymap', {
            'ctrl+e': function() {
                // todo
            }
        }); // 在App.vue中可以省略scope参数
    }
}
</script>
```

**注：**
在非`App.vue`中注册全局及交易级热键需要添加`global/trade`字段。
```js
this.$setHotkey(name, data, 'global');
```

#### 2.2 注册组件级热键
```html
// 当前vue文件
<template>
    <div>
        <aui-input v-hotkey='keymap'></aui-input>
    </div>
</template>
<script>
export default {
    data() {
        return {
            keymap: {}
        }
    },
    mounted() {
        this.$setHotkey('keymap', {
            'ctrl+e': function() {
                // todo
            }
        });
    }
}
</script>
```

### 3. 删除热键

```js
this.$delHotkey(name, shortcut[, scope]);
```

**注：只能用此方法删除热键。**

```html
// 当前vue文件
<template>
    <div>
        <aui-input v-hotkey='keymap'></aui-input>
    </div>
</template>
<script>
export default {
    data() {
        return {
            keymap: {}
        }
    },
    mounted() {
        this.$setHotkey('keymap', {
            'ctrl+e': function() {
                // todo
            }
        });
        
        // 删除
        this.$delHotkey('keymap', 'ctrl+e');
    }
}
</script>
```

| 参数 | 类型 | 可选值 | 说明 |
| ------- | ------ | ------------------ |
| name | string | - | 指令绑定的变量名 |
| data | object | - | 热键短语及执行的方法 |
| shortcut | string | - | 热键短语，如：'ctrl+e' |
| scope(可选) | string | 'global', 'trade' | 热键作用域 |
