# ab-logger@日志管理

日志级别为：`info`(提示)、`warn`(警告)、`debug`(调试)、`error`(错误)、`fatal`(致命)。

使用

```js
import { FrameLogger } from "ab-logger" // FrameLogger为框架级别日志
import { TradeLogger } from "ab-logger" // TradeLogger为交易级别日志

FrameLogger.info(message, info);
TradeLogger.debug(message, info);
```

例：

```js
FrameLogger.error("错误", new Error("This is a error!"));
TradeLogger.info("在XXX文件的XX位置", "这是一个信息");
```

| 参数     | 类型 | 说明 |
| -------- | --- | --- |
| message | string | 日志的相关描述信息 |
| info | - | 具体日志内容 |
