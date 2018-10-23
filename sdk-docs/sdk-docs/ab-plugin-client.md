# ab-plugin-client@客户端配置项

1.引入

```js
import { Client } from "ab-plugin-client"
```

2.使用

**关闭客户端**

```js
Client.closeClient();
```

**最小化客户端**

```js
Client.setMinimized();
```

**最大化客户端**

```js
Client.setMaxmized();
```

**获取客户端oid**

```js
let oid = Client.getOid();
```

| 事件     | 说明 | 参数 |
| -------- | --- | --- |
| closeClient | 关闭客户端 | - |
| setMinimized | 最小化客户端 | - |
| setMaxmized | 最大化客户端 | - |
| getOid | 获取客户端iod | - |