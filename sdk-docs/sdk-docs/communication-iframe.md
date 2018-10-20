# ab-manager-communication-iframe

父页面与iframe之间传递消息。

1. 引入
```js
    import { CommunicationIframe } from 'ab-manager-communication-iframe'
```
2. 父页面向子页面发送消息：
```js
    CommunicationIframe.sendMessage(iframeName, msg);
```
**iframe页面**(例)
```html
    <template>
        <iframe name="T10001" ></iframe>
    </template>
```
```js
    <script>
        CommunicationIframe.sendMessage('T10001', '向T10001发送的消息');
    </script>
```
> 注：切换交易存在焦点重置问题，由父元素向指定交易iframe发送消息重置焦点，传递的参数必须为`reset`。

```js
    CommunicationIframe.sendMessage(iframeName, "reset");
```

3. 子页面向父页面发送消息：

```js
    // 子页面 发送消息
    CommunicationIframe.popupMessage(msg);
    // 父页面 需要建立监听子页面请求 getMessage:接受消息的回调函数 接受一个参数为子页面发送的消息内容msg
    methods:{
        getMessage(e){
            // 接受消息的回调函数
            return;
        }
    }
    CommunicationIframe.unityMessage(this.getMessage);
```
> 由于只有一个父元素，所以不用指定`name`，直接传递数据(msg)即可。

> **CommunicationIframe Events**

|事件|说明|参数|
|-----|:-----:|:-----:|
|sendMessage|iframe页面向子页面发送消息|iframeName(发送消息的iframe的name),</br>msg(发送的消息内容,</br>由父元素向指定交易iframe发送消息重置焦点,传递的参数必须为`reset`)|
|popupMessage|子页面向iframe页面发送消息|msg(发送的消息内容)|
|unityMessage|iframe页面监听子页面的消息内容|callbackFun(接收消息的回调函数)|
