# ab-manager-services

管理页面调用的服务，包括向服务器发送请求以及外设调用。

> `config`用来设置是外设请求还是其他请求，可选参数，需额外引入。

1.引入

```js
import { ServicesManager } from 'ab-manager-services'
// 此处services-plugin.js以及services-names.js文件需要手动创建
// 每条服务的配置
import ServicesPlugin from '@/common/services-manager/services-plugin.js' // 相对路径 
// 定义服务名的常量
import ServicesNames from '@/common/services-manager/services-names.js' // 相对路径
// 定义统一错误处理信息的函数
import ServicesError from './common/services-manager/services-error.js' // 相对路径
// 在初始化的时候将plugin传入ServicesManager
Vue.use(ServicesManager, {plugin: ServicesPlugin, errorHandle: ServicesError});
```

2.发送请求：

```js
// 方法一：
ServicesManager.getService(serviceName, parameter).then(res => {
    // 回调函数
});

// 方法二：
ServicesManager.getService(ServiceName).customParam(...args).customConfig(configs).done().then(res => {})
```

> `customParam`和`customConfig`为service-plugin.js中自定的方法，支持链式调用。

例：

```js
import ServicesNames from '@/common/services-manager/services-names.js'

ServicesManager.getService(ServicesNames.LOGINSERVICE, {name: 'Jack'}).then(res => {
    // 回调函数
});
```

3.services-plugin.js解析：

可以加入配置：

```js
// 二者选一或者不选 分别是外设服务和常规服务端请求，在里面配置自定义参数
import Device from "@/common/services-manager/config-device"; // 相对路径
import Host from "@/common/services-manager/config-host"; // 相对路径
```

例：

```js
export default [
    {
        type: 'get', // string - 请求类型
        name: 'login', // string - 服务名称（serviceName）
        url: '/userLogin', // string - 请求地址
        customParam: function(param) { // function - 自定义参数类型
            // todo
            return param;
        },
        config: Host
    }
    // ...
]
```

> 如果配置config属性，config中的baseURL会覆盖原有的url。

3.1 自定义参数形式(customParam)

如果设置customParam属性，表示自定义参数形式，最终的参数类型就是customParam函数的返回值。

例3 —— 自定义参数形式：

```js
import ServicesNames from '@/common/services-manager/services-names.js'

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
