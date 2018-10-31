# ab-manager-services@服务管理

管理页面调用的服务，包括向服务器发送请求以及外设调用。

> `config`用来设置是外设请求还是其他请求，可选参数，需额外引入。

1.引入

```js
import { ServicesManager } from 'ab-manager-services'
// 此处services-plugin.js以及services-names.js文件需要手动创建
// 服务的配置
import ServicesPlugin, { serviceConfig as Config } from '@/common/managers/services-manager/services-plugin.js' // 相对路径 
// 定义服务名的常量
import ServicesNames from '@/common/managers/services-manager/services-names.js' // 相对路径
// 定义统一错误处理信息的函数
import ServicesError from './common/managers/services-manager/services-error.js' // 相对路径
// 在初始化的时候将plugin传入ServicesManager
Vue.use(ServicesManager, {plugin: ServicesPlugin, errorHandle: ServicesError, config: Config});
```

2.发送请求：

```js
ServicesManager.getService(serviceName[, parameter, config]).then(res => {
    // 回调函数
});
```

> `customParam`和`customConfig`为service-plugin.js中自定的方法，数组中参数可省略，两个参数分对应两个方法的入参。

例：

```js
import ServicesNames from '@/common/managers/services-manager/services-names.js'

ServicesManager.getService(ServicesNames.LOGINSERVICE, {name: 'Jack'}).then(res => {
    // 回调函数
});
//当需要修改头信息 可传入第三个参数
ServicesManager.getService(ServicesNames.LOGINSERVICE, {name: 'Jack'}, {headers:{"X-AmebaCloud-Token":""}}).then(res => {
    // 回调函数
});
```

3.services-plugin.js解析：

例：

```js
// 可在此处配置全局token相关内容
let serviceConfig = {
    timeout: 2000,
    headers: {}
};

export {
    serviceConfig
}

export default [
    {
        type: 'get', // string - 请求类型
        name: 'login', // string - 服务名称（serviceName）
        url: '/userLogin', // string - 请求地址
        customParam: function(param) { // function - 自定义参数类型
            // todo
            return param;
        },
        customConfig: function(config) { // function - 自定义参数类型
            // todo
            return config;
        }
    }
    // ...
]
```

> 如果配置config属性，config中的baseURL会覆盖原有的url。

3.1 自定义参数形式(customParam)

如果设置customParam属性，表示自定义参数形式，最终的参数类型就是customParam函数的返回值。

例3 —— 自定义参数形式：

```js
import ServicesNames from '@/common/managers/services-manager/services-names.js'

ServicesManager.getService(ServicesNames.LOGINSERVICE, {name: 'Jack', age: 20}).then(res => {
    // 回调函数
});
```

**services-plugin.js**
```js
customParam: function(param) {
    param.height = 180;
    return param;
}
```

最终传参为：

```js
{
    name: "Jack",
    age: 20,
    height: 180
}
```
3.2 自定义config形式(customConfig)

如果设置customConfig属性，表示自定义config形式，最终的config类型就是customConfig函数的返回值。

例3 —— 自定义config形式：

```js
import ServicesNames from '@/common/managers/services-manager/services-names.js'

ServicesManager.getService(ServicesNames.LOGINSERVICE, {name: 'Jack', age: 20}, {headers:{"X-AmebaCloud-Token":""}}).then(res => {
    // 回调函数
});
```

**services-plugin.js**
```js
customConfig: function(config) {
    config.timeout = 15000;
    return config;
}
```

最终传参为：

```js
{
    headers: {"X-AmebaCloud-Token":""},
    timeout: 15000
}
```
4.错误处理

首先先定义错误处理函数

**services-error.js**
```js
export default function(scope, opts) {
    scope.$aui.message.show({
        type: 'error',
        message: '这是一条错误信息：' + opts
    });
}
```

使用Services.error函数：

```js
ServicesManager.error(this, options);
```

| 参数     | 类型 | 说明 |
| -------- | --- | --- |
| serviceName | string | 服务名称 |
| parameter | - | 请求中的参数 |

services-plugin.js参数

| 参数     | 类型 | 说明 |
| -------- | --- | --- |
| type | string | 请求类型 |
| name | string | 定义的服务名称 |
| url | string | 请求路径 |
| customParam(可选) | function | 自定义参数的方法 |
| config(可选) | object | 自定义的配置 |

services-error.js参数

| 参数     | 类型 | 说明 |
| -------- | --- | --- |
| scope | - | 当前作用域 |
| opts | - | 准备处理的数据 |

**配置参数`ABConfig`:**

| 参数     | 类型 | 说明 | 默认值 |
| -------- | --- | --- | --- |
| ABConig.hostIp | array/string | 发送请求的IP | http://127.0.0.1:8080 |
| ABConig.MAX_COUNT | number | 请求重发的最大次数 | 0 |
