# ab-plugin-client@客户端配置项

1.引入

```js
import { Client } from 'ab-plugin-client';
```

2.事件方法使用说明

> **关闭客户端**

```js
Client.closeClient().then(res => {
  // todo
});
```

> **最小化客户端**

```js
Client.setMinimized().then(res => {
  // todo
});
```

> **最大化客户端**

```js
Client.setMaxmized().then(res => {
  // todo
});
```

> **获取客户端 oid**

```js
let oid = '';
Client.getOid().then(res => {
  // todo
  oid = res.oid;
});
```

> **关机操作**

```js
Client.closeSystem().then(res => {
  // todo
});
```

> **重启操作**

```js
Client.restartSystem().then(res => {
  // todo
});
```

> **获取客户端ip**

```js
Client.getClientIp().then(res => {
  // todo
  console.log(res.clientIp)
});
```

> **获取客户端appId**

```js
let clientIp = "192.168.31.147"
Client.getAppID(clientIp).then(res => {
  // todo
  console.log(res.appId)
});
```

> **获取客户端Mac**

```js
let clientIp = "192.168.31.147"
Client.getMac(clientIp).then(res => {
  // todo
  console.log(res.mac)
});
```

**Events promise 函数**

| 事件          |      说明      | 参数 |
| ------------- | :------------: | :--: |
| closeClient   |   关闭客户端   |  -   |
| setMinimized  |  最小化客户端  |  -   |
| setMaxmized   |  最大化客户端  |  -   |
| getOid        | 获取客户端 oid |  -   |
| closeSystem   |    关机操作    |  -   |
| restartSystem |    重启操作    |  -   |
| getMac        | 获取客户端 Mac地址 |  clientIp  |
| getAppId      | 获取客户端 应用标识 |  clientIp   |
| getClientIp   | 获取客户端 客户端Ip地址    |  -   |
