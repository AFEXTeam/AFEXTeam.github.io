# ab-manager-device@外设调用及配置

1.引入

```js
import { DeviceManager } from "ab-manager-device"
```

2.使用

**获取外设配置信息**

```js
DeviceManager.getDeviceList();
```

**设置外设配置**

```js
DeviceManager.setDeviceList(deviceConfig);
```

**调用外设**

```js
DeviceManager.getDevice(type,optArg).then(res => {
    // todo
});
```

| 参数     | 类型 | 说明 | 默认值 | 可选值 |
| -------- | --- | --- | --- | --- |
| deviceConfig | object | 外设配置信息 | — | — |
| type | string | 设备类型 | — | 'NIc'/'Ic'/'Id'/'Msf'/'Fp'/'Pin'/'Gwq'/'Prt' |
| optArg | object | 调用外设所需参数 | — | — |
