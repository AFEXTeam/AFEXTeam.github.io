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



## 参数

| 参数     | 类型 | 说明 | 可选值 |
| -------- | --- | --- | --- |
| key | string | 保存的变量名 | - |
| value | - | 保存的数据 | - |