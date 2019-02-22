# ab-plugin-device@外设配置项

1.引入

```js
    import { DeviceSetting } from "ab-plugin-device"
```

2.事件方法的使用

> **获取外设列表**

```js
    DeviceSetting.getDeviceList().then(res=>{
        // todo
    });
```

> **设置外设配置信息**

```js
    DeviceSetting.setDeviceList(setting).then(res=>{
        // todo
    });
```
> **获取abc 监听adssocket端口**

```js
    DeviceSetting.getAbcSocketPort().then(res=>{
        // todo
    });
```

> **获取adssocket端口**

```js
    DeviceSetting.getDeviceSocketPort().then(res=>{
        // todo
    });
```

> **判断ads是否启动成功**

```js
    DeviceSetting.isAdsConnect().then(res=>{
        // todo
    });
```

> **根据传入外设类型获取外设配置**

```js
    DeviceSetting.getOneTypeDeviceConfig(adsType,adsQuery).then(res=>{
        // todo
    });
```

> **订阅客户端原生层当ads启动后回调的js方法**

```js
    DeviceSetting.deviceSubscribe(function(msg,res){
        // todo
    })
```
> **取消订阅客户端原生层当ads启动后回调的js方法**

```js
    DeviceSetting.deviceUnsubscribe()
```

> **设置外设ads链接url**

```js
  import { DeviceSetting } from 'ab-plugin-device'
  let adsUrl="http://127.0.0.1:3306";
  let result = await DeviceSetting.setAdsPreference(adsUrl);
```
**Events promise函数**

|事件名|说明|参数|
|-----|:----:|:----:|
|getDeviceList|获取外设列表|-|
|setDeviceList|设置外设配置信息|setting: 配置的json字符串|
|getDeviceSocketPort|获取adssocket端口|-|
|isAdsConnect|判断ads是否启动成功|-|
|deviceSubscribe|订阅客户端原生层当ads启动后回调的js方法|fun:订阅消息的回调函数|
|deviceUnsubscribe|取消订阅客户端原生层当ads启动后回调的js方法|-|
|getOneTypeDeviceConfig|根据传入外设类型获取外设配置|adsType:String 外设类型;adsQuery:String 是否从ads获取外设配置信息|
|setAdsPreference|设置外设ads链接url|adsUrl:ads的链接url|
