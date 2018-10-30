# ab-manager-websocket@websocket连接

必要配置:
**configjs**
```js
let ABConfig = {
    socketIp: ["ws://xxx"]
}
```
1. 引入
```js
    import { WebsocketManager } from 'ab-manager-websocket';
```
2. 事件使用说明
```js
    // 实例
    let WebsocketManager = new WebsocketManager({
        id: "oid_1"
    });
```

> 连接建立时触发
```js
    WebsocketManager.onopen = function () {
        WebsocketManager.send({
            id: "oid_1",
            data: "onopen success"
        });
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
        console.log('close...');
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
    WebsocketManager.send({
        id: "",
        data: ""
    });
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
    import { WebsocketManager } from "ab-manager-websocket"
    export default {
    name: "HelloWorld",
    data() {
        return {
        ws: undefined
        };
    },
    mounted() {
        this.ws = new WebsocketManager({"url":"ws://127.0.0.1:50010/ws/broadcast", id: "oid_1"});
        let _this = this;
        this.ws.onopen = function(evt) {
            _this.ws.send({
                id: "oid_1",
                data: "onopen success"
            });
        };
    }
```
> **WebsocketManager Attributes**

| 参数             | 说明                                                          | 类型    | 默认值      |
| ---------------- | :-----------------------------------------------------------: | :-----: | :---------: |
| url              | websocket服务端接口在config配置socketIp字段 | Array  | - |
| id              | websocket连接唯一标识 | String/number  | - |
| pingTimeOut      | 每隔15秒发送一次心跳请求                                      | Number  | 15000       |
| pongTimeOut      | ping消息发送之后,10秒内没收到后端消息便会认为连接断开         | Numebr  | 10000       |
| reconnectTimeOut | 尝试重连的间隔时间                                            | Number  | 2000        |
| pingMsg          | ping消息内容                                                  | String  | "heartbeat" |
| forbidReconnect  | 是否进行重连操作                                              | Boolean | false       |

> **WebsocketManager Events**

| 事件名      | 说明                       | 参数  |
| ----------- | :------------------------:| :---: |
| onopen      | 连接建立时触发             | event |
| onerror     | 通信发生错误时触发         | event |
| onmessage   | 客户端接收服务端数据时触发  | event |
| onclose     | 连接关闭时触发             | event |
| onreconnect | 发生重连触发               | event |

> **WebsocketManager Methods**

| 方法名 | 说明     | 参数       |
| ------ | :------: | :--------: |
| send   | 发送消息 | 消息的内容 |
| close  | 关闭连接 | -          |
