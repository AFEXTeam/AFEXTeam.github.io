# ab-manager-storage@全局缓存数据

调用外设。

1.引入

```js
// main.js

import { StorageManager } from "ab-manager-storage";
import StorageName from "@/common/storage-manager/storage-name.js";
Vue.use(StorageName);
```

2.使用：

```js
import { StorageManager } from "ab-manager-storage";
    
StorageManager.setStore(key, value);
```

例：

```js
// 设置数据
StorageManager.setStore("name", "daiqiang");
// 获取数据
let username = StorageManager.getStore("name");
// 移除数据
StorageManager.removeStore("name");
// 移除全部数据
StorageManager.removeStore();
```

> **StorageManager Events**

| 事件        | 说明               | 参数                                            |
| :-----------: | :------------------: | :-------------: |
| setStore    | 存储数据           | key:保存的变量名;value:需要保存的数据           |
| getStore    | 获取已经存储的数据 | key:保存的变量名                                |
| removeStore | 清空存储的数据     | key:保存的变量名;不传参数则清空所有已保存的数据 |