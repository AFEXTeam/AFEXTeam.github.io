# ab-plugin-embed@前端内嵌应用程序

1.引入

```js
import { MFC_IE } from "ab-plugin-embed"
import { Ole_IE } from "ab-plugin-embed"
import { Ole_Frame } from "ab-plugin-embed"
```

2.使用
-------------
### 2.1 MFC_IE

init
```js
MFC_IE.init('aw').then(res=>{
    // todo
});
```

| 事件     | 说明 | 参数 |
| -------- | --- | --- |
| init |  发送内嵌请求初始化 | id:当前内嵌组件id |

setUrl
```js
MFC_IE.setUrl('aw','http://www.baidu.com/').then(res=>{
    // todo
});
```

| 事件     | 说明 | 参数 |
| -------- | --- | --- |
| setUrl |  发送内嵌请求初始化 | id:当前内嵌组件id; url:访问地址 |

setUrl
```js
MFC_IE.setUrl('aw','http://www.baidu.com/').then(res=>{
    // todo
});
```

| 事件     | 说明 | 参数 |
| -------- | --- | --- |
| setUrl |  设置ie浏览器地址 | id:当前内嵌组件id; url:访问地址 |

refreshUrl
```js
MFC_IE.refreshUrl('aw').then(res=>{
    // todo
});
```

| 事件     | 说明 | 参数 |
| -------- | --- | --- |
| refreshUrl |  网页刷新 | id:当前内嵌组件id |

getLocationURL
```js
MFC_IE.getLocationURL('aw').then(res=>{
    // todo
});
```

| 事件     | 说明 | 参数 |
| -------- | --- | --- |
| getLocationURL |  获取当前浏览器url地址 | id:当前内嵌组件id |

setSilent
```js
MFC_IE.setSilent('aw',silent).then(res=>{
    // todo
});
```

| 事件     | 说明 | 参数 |
| -------- | --- | --- |
| setSilent |  设置ie是否禁用警告窗口 | id:当前内嵌组件id; silent:boolean,是否禁用标识|

execute
```js
let script = `document.getElementById('username').value='${
            this.username
            }';document.getElementById('userTypePwd').value='${
            this.password}';`;
MFC_IE.execute('aw',script).then(res=>{
    // todo
});
```

| 事件     | 说明 | 参数 |
| -------- | --- | --- |
| execute |  执行浏览器脚本 | id:当前内嵌组件id; script:string,执行script脚本|

finish
```js
MFC_IE.finish('aw').then(res=>{
    // todo
});
```

| 事件     | 说明 | 参数 |
| -------- | --- | --- |
| finish |  执行销毁浏览器 注意：不允许在vue beforeDestroy中使用 | id:当前内嵌组件id |

delay_finish
```js
let delayTime = 1000;
MFC_IE.delay_finish('aw',delayTime).then(res=>{
    // todo
});
```

| 事件     | 说明 | 参数 |
| -------- | --- | --- |
| delay_finish |  延时执行销毁浏览器 注意：不允许在vue beforeDestroy中使用 | id:当前内嵌组件id;delayTime:延时时间(毫秒) |

setValue
```js
let domId = 'input_name';
let domValue = 'huangguan';
MFC_IE.setValue('aw',domId,domValue).then(res=>{
    // todo
});
```

| 事件     | 说明 | 参数 |
| -------- | --- | --- |
| setValue | 为浏览器中某个dom对象设置值 | id:当前内嵌组件id;domId:浏览器内操作dom元素的id；domValue：浏览器内操作dom元素的value值 |

submit
```js
let domName = 'login';
MFC_IE.submit('aw',domName).then(res=>{
    // todo
});
```

| 事件     | 说明 | 参数 |
| -------- | --- | --- |
| submit | 浏览器中提交表单 | id:当前内嵌组件id;domName:浏览器内操作表单的dom元素名称 |

submitById
```js
let domId = 'button_login';
MFC_IE.submitById('aw',button_login).then(res=>{
    // todo
});
```

| 事件     | 说明 | 参数 |
| -------- | --- | --- |
| submitById | 根据浏览器中提交表单提交按钮dom-id来触发表单提交 | id:当前内嵌组件id;domId:浏览器内操作表单的dom元素Id |

getHtml
```js
MFC_IE.getHtml('aw').then(res=>{
    // todo
});
```

| 事件     | 说明 | 参数 |
| -------- | --- | --- |
| getHtml | 获取某个指定内嵌浏览器的全部html(返回的为html的Base64串) | id:当前内嵌组件id |


### 2.2 OLE_IE
其中与MFC_IE调用方式一致的为：
- init
- setUrl
- execute
- finish
- delay_finish
- setValue
- submit
- submitById
- getHtml

#### 特殊方法为：

doLogin
```js
let url = "https://mail.agree.com.cn"
OLE_IE.doLogin('aw',url).then(res=>{
});
```

| 事件     | 说明 | 参数 |
| -------- | --- | --- |
| doLogin | 触发浏览器登陆操作| id:当前内嵌组件id; url：登录url地址|

doLogout
```js
let url = "https://mail.agree.com.cn"
OLE_IE.doLogout('aw',url).then(res=>{
});
```

| 事件     | 说明 | 参数 |
| -------- | --- | --- |
| doLogout | 触发浏览器登出操作| id:当前内嵌组件id; url：登录url地址|

### 2.3 OLE_Frame

init
```js
OLE_Frame.init('aw').then(res=>{
});
```

| 事件     | 说明 | 参数 |
| -------- | --- | --- |
| init | oleFrame初始化操作| id:当前内嵌组件id|

dispose
```js
OLE_Frame.dispose('aw').then(res=>{
});
```

| 事件     | 说明 | 参数 |
| -------- | --- | --- |
| dispose | oleFrame销毁操作| id:当前内嵌组件id  注意：不允许在vue beforeDestroy中使用|

openFile
```js
let filePath = 'C:/Users/CrownHwang/Desktop/test.docx'

OLE_Frame.openFile('aw',filePath).then(res=>{
});
```

| 事件     | 说明 | 参数 |
| -------- | --- | --- |
| openFile | 打开文件| id:当前内嵌组件id; filePath:打开文件路径|

searchWords
```js
let words = 'hello'
OLE_Frame.searchWords('aw',words).then(res=>{
});
```

| 事件     | 说明 | 参数 |
| -------- | --- | --- |
| searchWords | 查找文字| id:当前内嵌组件id; words:查找文字|




