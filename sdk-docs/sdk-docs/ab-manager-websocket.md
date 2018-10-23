# ab-manager-websocket@websocket连接


1. 引入
```js
    import WebsocketManager from 'ab-manager-websocket';
```
2. 事件使用说明
```js
    // 实例
    let WebsocketManager = new WebsocketManager({
        url: 'ws://xxxxxxx'
    });
```

> 连接建立时触发
```js
    WebsocketManager.onopen = function () {
        console.log('connect success');
        WebsocketManager.send('hello server');
    }
```
> 通信发生错误时触发
```js
    WebsocketManager.onerror = function (e) {
        console.log(`onerror: ${e}`);
    }
```
> 客户端接收服务端数据时触发
```js
    WebsocketManager.onmessage = function (e) {
        console.log(`onmessage: ${e.data}`);
    }
```
> 连接关闭时触发
```js
    WebsocketManager.onclose = function (e) {
        console.log('close...);
    }
```
> 发生重连触发
```js
    WebsocketManager.onreconnect = function () {
        console.log('reconnecting...');
    }
```
3. 方法使用说明
> send 发送消息
```js
    WebsocketManager.send('hello server');
```
> close 关闭连接
```js
    WebsocketManager.close('hello server');
```
4. websocket的实例
```js
    WebsocketManager.ws  
```
> 注：如果需要操作websocket的其他属性,直接操作WebsocketManager.ws

5. 使用案例
```js
    import WebsocketManager from "ab-manager-websocket"
    export default {
    name: "HelloWorld",
    data() {
        return {
        ws: undefined
        };
    },
    mounted() {
        this.ws = new WebsocketManager({"url":"ws://127.0.0.1:50010/ws/broadcast"});
        let initObj = {
                type: "init", //init->初始化操作,wspush->推送消息 ...
                id: "oid_1", //init->为本机id,wspush->推送的目标id ...
                data:"推送的消息内容" //init->无,wspush->推送的消息内容 ...
            };
        let _this = this;
        this.ws.onopen = function(evt) {
            console.log("Connection open ...", evt);
            _this.ws.send(JSON.stringify(initObj));
        };
    }
```
> **WebsocketManager Attributes**

|参数|说明|类型|默认值|
|-----|:-----:|:-----:|:-----:|
|url|websocket服务端接口.可以直接传入,也可以在config配置socket字段|String||
|pingTimeOut|每隔15秒发送一次心跳请求|Number|15000|
|pongTimeOut|ping消息发送之后,10秒内没收到后端消息便会认为连接断开|Numebr|10000|
|reconnectTimeOut|尝试重连的间隔时间|Number|2000|
|pingMsg|ping消息内容|String|"heartbeat"|
|forbidReconnect|是否进行重连操作|Boolean|false|

> **WebsocketManager Events**

|事件名|说明|参数|
|-----|:-----:|:-----:|
|onopen|连接建立时触发|event|
|onerror|通信发生错误时触发|event|
|onmessage|客户端接收服务端数据时触发|event|
|onclose|连接关闭时触发|event|
|onreconnect|发生重连触发|event|

> **WebsocketManager Methods**

|方法名|说明|参数|
|-----|:-----:|:------:|
|send|发送消息|消息的内容|
|close|关闭连接|-|
