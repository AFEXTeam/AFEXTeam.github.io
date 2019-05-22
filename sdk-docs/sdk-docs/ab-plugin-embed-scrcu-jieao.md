# ab-plugin-embed-scrcu-jieao@前端内嵌捷奥影像控件

1.引入

```js
import { Jieao_Exe } from "ab-plugin-embed-scrcu-jieao"
```

2.使用
-------------

init
```js
Jieao_Exe.init(initJson).then(res=>{
    // todo
});
```

| 事件     | 说明 | 参数 |
| -------- | --- | --- |
| init |  发送内嵌请求初始化 | Json格式的入参，键名：displayMode，ip，port，poolName，userId，appId，treeId，bizId |

show
```js
Jieao_Exe.show().then(res=>{
    // todo
});
```

| 事件     | 说明 | 参数 |
| -------- | --- | --- |
| show |  发送内嵌请求初始化显示界面，在init之后立刻执行 | 空 |

commit
```js
Jieao_Exe.commit(param, bizid).then(res=>{
    // todo
});
```

| 事件     | 说明 | 参数 |
| -------- | --- | --- |
| commit |  提交 | param:影像提交方式 0-批次下全部提交，1-批次下勾选影像提交 注意：如果无param节点，则默认为0-批次下全部提交；bizid:影像提交的批次号 |

showImage
```js
Jieao_Exe.showImage(paramJson).then(res=>{
    // todo
});
```

| 事件     | 说明 | 参数 |
| -------- | --- | --- |
| showImage |  影像调阅 | Json格式的入参，键名：bizid影像批次号 或者是  path本地调阅文件的路径，只能二选一|

finish
```js
Jieao_Exe.finish().then(res=>{
    // todo
});
```

| 事件     | 说明 | 参数 |
| -------- | --- | --- |
| finish |  关闭控件 | 空 |
