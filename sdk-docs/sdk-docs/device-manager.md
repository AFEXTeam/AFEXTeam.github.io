# ab-manager-device

调用外设。

1.引入

```js
import { DeviceManager } from "ab-manager-device";
```

2.使用：

```js
DeviceManager.invokeDevice(invokeType, deviceType, commonArg, optArg).then(res => {
    // todo
});
```

例 —— 二代证：

```js
DeviceManager.invokeDevice("http", "Id", {
    Id: "Id1",
    Method: "ReadCard",
    Args: '{"mode":"1"}',
    Key: "a"
}).then(res => {
    console.log(res); // 读取二代证返回的信息
});

```

例 —— 打印：

```js
DeviceManager.invokeDevice("http", "Prt", {
    Id: "Prt1",
    Method: "Print",
    Args: "",
    Key: "b"
},
{
    printData: {
        AccountNum: "6217000000",
        TradeSerialNum: "123456789",
        AcctName: "代强",
        TradeMoney: "10000"
    },
    aftPath: "/www/print/T10010.aft",
    calibrationPath: "/www/print/calibration.prt"
}).then(res => {
    console.log(res); // 打印完成后返回的信息
});

```

## 调用方法的参数

| 参数     | 类型 | 说明 | 可选值 |
| -------- | --- | --- | --- |
| invokeType | string | 调用外设的方式 | "http" |
| deviceType | string | 调用外设的类型 | Id/Msf/Ic/Fp/Pin/Gwq/Scan/Prt/Ic_iccall/PinEncrypt |
| commonArg | object | 调用外设的公共参数 | - |
| optArg | object | 调用外设的其他参数 | - |

## 方法中参数的字段

| 参数     | 类型 | 说明 | 可选值 |
| -------- | --- | --- | --- |
| Id | string | 设备id | - |
| Method | string | 调用外设的方法 | - |
| Args | string(json) | 参数（json字符串） | - |
| Key | string | 占用标识 | - |
| ReadTimeout | number | 读超时时间（默认：20） | - |
| WriteTimeout | number | 写超时时间（默认：20） | - |
| IsOccupy | string | 是否占用（默认："0"） | - |
| ListenPort | string | 监听端口（默认：""） | - |
| printData | object | 打印数据 | - |
| aftPath | string | 打印的.aft文件路径 | - |
| calibrationPath | string | 打印的.prt文件路径 | - |