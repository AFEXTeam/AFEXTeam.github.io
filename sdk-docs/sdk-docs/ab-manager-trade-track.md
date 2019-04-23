# ab-manager-trade-track@交易链路追踪

交易链路追踪管理器，根据不同渠道进行交易的链路追踪管理。

> `channel`用来设置渠道标识，需要在交易工程static文件夹下的config.js中配置，例如：
```js
var ABConfig = {
  hostIp: ["http://192.9.200.137:50002"],
  socketIp: ["ws://192.9.200.137:8888/websocket"],
  channel: "TEClient" // =>此配置未交易渠道标识 TEClient为柜面前端交易
};
```
**渠道标识编号**

|标识|说明|平台|
|-----|:----:|:----:|
|TEClient|柜面渠道|Java-PC|
|MOClient|厅堂渠道|移动|
|MGClient|管理V端渠道|Web-PC|
|CQClient|排队机渠道|Java-PC|


1.引入

```js
import { TradeTrack } from "./ab-manager-trade-track";
```

2.事件方法的使用

> **申请tradeId**

#### getTradeId
```js
let result = await TradeTrack.getTradeId("T1001");
this.tradeId1 = result.tradeId;
```
```js
let result = await TradeTrack.getTradeId("T1001");
this.tradeId1 = result.tradeId;

let childResult = await TradeTrack.getTradeId("T1001",this.tradeId1)
this.childTradeId = childResult.tradeId
```

**Events promise函数**

|事件名|说明|参数|
|-----|:----:|:----:|
|getTradeId|申请tradeId|tradeName:String 交易名称;parentTradeId:String 非必输，父交易tradeId|

> **根据tradeId申请requestId**

#### getRequestId
```js
let result1 = await TradeTrack.getRequestId(this.tradeId1);
this.requestId1 = result1.requestId;
```

**Events promise函数**

|事件名|说明|参数|
|-----|:----:|:----:|
|getRequestId|根据tradeId申请RequestId|tradeId:String 交易tradeId|

> **根据tradeId申请requestId**

#### getRequestId
```js
let result1 = await TradeTrack.getRequestId(this.tradeId1);
this.requestId1 = result1.requestId;
```

**Events promise函数**

|事件名|说明|参数|
|-----|:----:|:----:|
|getRequestId|根据tradeId申请RequestId|tradeId:String 交易tradeId|

> **清除tradeId**

#### remove
```js
let result1 = await TradeTrack.remove(this.tradeId1);
```

**Events promise函数**

|事件名|说明|参数|
|-----|:----:|:----:|
|remove|清除tradeId|tradeId:String 交易tradeId|