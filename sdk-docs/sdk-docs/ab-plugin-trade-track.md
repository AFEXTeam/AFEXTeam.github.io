# ab-manager-trade-track@交易链路追踪

交易链路追踪管理器，根据不同渠道进行交易的链路追踪管理。

1.引入

```js
import { TradeTrack } from "./ab-manager-trade-track";
```

2.事件方法的使用
> **申请traceId**
```js
let channelId = "01";
let result = TradeTrack.getTraceId(channelId);
```
`channelId`用来设置渠道标识，需要在申请traceId时传入，例如：

**渠道标识编号**

|channelId|说明|平台|
|-----|:----:|:----:|
|01|柜面渠道|Java-PC|
|02|自助渠道|.net-PC|
|03|厅堂渠道|移动|
|04|管理V端渠道|Web-PC|
