# ab-plugin-device-event-handler@外设调用事件处理器

1.引入

```js
import { DeviceEventHandler } from 'ab-plugin-device-event-handler';
```

2.事件方法的使用

> **外设调用事件处理器**

```js
DeviceEventHandler.deviceEventHandler(vendor, method, deviceType, args).then(res => {
  // todo
});
```

**Events promise 函数**

| 事件名             |        说明        | 参数 |
| ------------------ | :----------------: | :--: |
| deviceEventHandler | 外设调用事件处理器 |  vendor:String 厂商名称;method:String 外设方法; deviceType:String 外设类型, args:Map 外设方法参数   |
