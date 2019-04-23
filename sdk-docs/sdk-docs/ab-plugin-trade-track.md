# ab-plugin-trade-track@日志链路追踪

1.引入

```js
import { TradeTrack } from "./ab-plugin-trade-track";
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