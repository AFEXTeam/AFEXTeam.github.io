# ab-core

1.引入

```js
import { EventHub } from 'ab-core';
```

2.订阅

```js
EventHub.subscribe(topic, fun);
```
栗：
```js
let topic = "testTopic";
let testFn = function(msg, data) {
    console.log(msg, "hello " + data); // "testTopic" "hello agree"
}
EventHub.subscribe(topic, testFn);
```

3.发布

```js
EventHub.publish(topic, data)
```
栗：
```js
let data = "agree";
EventHub.publish("testTopic", data)
```

4.取消订阅

```js
EventHub.unsubscribe(topic); // topic为空取消所有订阅
```
栗：
```js
EventHub.unsubscribe("testTopic");
EventHub.unsubscribe();
```

| 参数     | 类型 | 说明 |
| -------- | --- | --- |
| topic | string | 订阅的主题/标题 |
| fun | function | 订阅的方法 |
| msg | string | 订阅函数的第一个参数，为topic |
| data(可选) | - | 发布时传递给订阅方法的参数 |