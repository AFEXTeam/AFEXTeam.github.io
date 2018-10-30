# ab-plugin-device@外设配置项

1.引入

```js
import { DeviceSetting } from "ab-plugin-device"
```

2.使用

**获取外设列表**

```js
DeviceSetting.getDeviceList();
```

**设置外设配置信息**

```js
DeviceSetting.setDeviceList(setting);
```

**获取adssocket端口**

```js
DeviceSetting.getDeviceSocketPort();
```

**判断ads是否启动成功**

```js
DeviceSetting.isAdsConnect();
```

**订阅客户端原生层当ads启动后回调的js方法**

```js
// main.js
DeviceSetting.deviceSubscribe(function(msg,res){
    // todo
})
```