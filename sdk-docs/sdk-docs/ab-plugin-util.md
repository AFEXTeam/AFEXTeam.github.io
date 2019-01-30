# ab-plugin-util@前端应用工具类

## FileUtil工具类

1.引入
-------------
```js
import { FileUtil } from "ab-plugin-util"
import { CodecUtil} from "ab-plugin-util"
```

2.使用
-------------
readClientFile
```js
let filePath = "C:/test.log"
let offset = 0
let size = -1
FileUtil.readClientFile(filePath,...[offset,size]).then(res=>{
    // todo
});
```

downloadFile
```js
let remotePath = "C:/test.log"
let localPath = "C:/"
FileUtil.downloadFile(remotePath,localPath).then(res=>{
    // todo
    console.log(res.downloadFile)
});
```

clientFileCreate
```js
import {FileUtil} from 'ab-plugin-util'
let result = await FileUtil.clientFileCreate(filePath);
```

clientFileDelete
```js
import {FileUtil} from 'ab-plugin-util'
let result = await FileUtil.clientFileDelete(filePath);
```

clientFileExist
```js
import {FileUtil} from 'ab-plugin-util'
let result = await FileUtil.clientFileExist(filePath);
```

clientFileReadLines
```js
import {FileUtil} from 'ab-plugin-util'
let result = await FileUtil.clientFileReadLines(filePath,startLines,endLines);
```

clientFileRename
```js
import {FileUtil} from 'ab-plugin-util'
let result = await FileUtil.clientFileRename(oldName,newName);
```

writeClientFile
```js
 let filePath = "E:\\testdownload\\test.txt"; //文件路径
 let content = "123456"; //写入文件的内容
 let append = "true"; //是否追加写入
 let result = await CodecUtil.writeClientFile(filePath, content, append);
```

desHandler
```js
 let source = "123456";
 let mode = "encrypt"; //加密标志 "decrypt" //解密标志
 let key = "3132333435363738"; //DES秘钥
 let result = await CodecUtil.desHandler(source, mode, key);
```



3.事件
-------------
| 事件     | 说明 | 参数 |
| -------- | --- | --- |
| readClientFile | 内嵌程序 | filePath : String  offset : Number size : Number |
| downloadFile | 文件下载 | remotePath : String  localPath : String |
| writeClientFile | 写客户端文件 | filePath : String  content : String append : boolean |
| desHandler | 编码工具 | source : String  mode : Number size : key |


4.参数说明
-------------
### FileUtil
#### readClientFile
| 事件     | 说明 | 类型 | 默认值
| -------- | --- | --- | ---|
| filePath | 文件路径 | String | null|
| offset | 偏移量 | Number | 0(不偏移) 非必输
| size | 读取量 | Number |-1(全部读取) 非必输
#### downloadFile
| 事件     | 说明 | 类型 | 默认值
| -------- | --- | --- | ---|
| remotePath | 服务端文件地址 | String | null
| localPath | 本地文件地址 | String | null
#### clientFileCreate
| 事件     | 说明 | 类型 | 默认值 |
| -------- | --- | --- | --- | --- |
| filePath | 文件路径 | String | null|
#### clientFileDelete
| 事件     | 说明 | 类型 | 默认值 |
| -------- | --- | --- | ---| --- |
| filePath | 文件路径 | String | null|
#### clientFileExist
| 事件     | 说明 | 类型 | 默认值 |
| -------- | --- | --- | ---|
| filePath | 文件路径 | String | null|
#### clientFileReadLines
| 事件     | 说明 | 类型 | 默认值
| -------- | --- | --- | ---|
| filePath | 文件路径 | String | null |
| startLines | 起始行数 | String | null |
| endLines | 终结行数 | String | null |
#### writeClientFile
| 事件     | 说明 | 类型 | 默认值
| -------- | --- | --- | ---|
| filePath | 文件路径 | String | null |
| content | 写入文件的内容 | String | null |
| append | 是否追加写入 | boolean | null |
-------------
### CodecUtil
#### desHandler
| 事件     | 说明 | 类型 | 默认值
| -------- | --- | --- | ---|
| source | 源字符串 | String |null
| mode | 加密标志 | String |"encrypt"加密 "decrypt"解密
| key | 秘钥 | String |null
