# ab-plugin-util@前端应用工具类

## FileUtil工具类

1.引入
-------------
```js
import { FileUtil } from "ab-plugin-util"
import { CodecUtil} from "ab-plugin-util"
import { ExportUtil} from "ab-plugin-util"
```

2.使用
-------------
listToExcel
```js
let data = [
    ["1","name","sexual","age"],
    ["2","huangguan","male","30"],
    ["3","liudexin","male","29"]
]
let sheetName = "sheet1" 非必输
let fontName = "宋体" 非必输
let fontSize = 10 非必输
let fontColor = black 非必输
let backgroundColor = -1 默认无色 非必输
let path = "D:\\test.xls"
await ExportUtil.listToExcel(data,path,sheetName,fontSize,fontName,fontColor,backgroundColor);
```

readClientFile
```js
let filePath = "C:/test.log"
let encoding = "gbk"
let offset = 0
let size = -1
FileUtil.readClientFile(filePath,encoding,...[offset,size]).then(res=>{
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
 let result = await FileUtil.writeClientFile(filePath, content, append);
```

uploadFile
```js
 let localPath = "C:\\test.txt"; //文件路径
 let remotePath = "/home/abs/fileContainer/test.txt"; //写入文件的内容
 let result = await FileUtil.uploadFile(localPath, remotePath);
```

getClientFileAsSavePath
```js
let type = ["jpeg","txt","doc"];
let behavior = "open"
let result = await FileUtil.getClientFileAsSavePath(type,behavior);
    //or
let result = await FileUtil.getClientFileAsSavePath();
```

desHandler
```js
 let source = "123456";
 let mode = "encrypt"; //加密标志 "decrypt" //解密标志
 let key = "3132333435363738"; //DES秘钥
 let result = await CodecUtil.desHandler(source, mode, key);
```

cryptoHandler
```js
let filePath = "C://test.txt"
let cryptoType = "SM3" //"SM3" SM3方式加密 "Md5"获取文件md5
let result = await CodecUtil.cryptoHandler(filePath,cryptoType)
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
#### uploadFile
| 事件     | 说明 | 类型 | 默认值
| -------- | --- | --- | ---|
| localPath | 本地文件路径 | String | null |
| remotePath | 服务端文件路径 | String | null |
#### getClientFileAsSavePath
| 事件     | 说明 | 类型 | 默认值
| -------- | --- | --- | ---|
| fileTypesList | 支持打开文件的类型 | List | null |
| behavior | 模态对话框打开样式 | String | "open" |
-------------
### CodecUtil
#### desHandler
| 事件     | 说明 | 类型 | 默认值
| -------- | --- | --- | ---|
| source | 源字符串 | String |null
| mode | 加密标志 | String |"encrypt"加密 "decrypt"解密
| key | 秘钥 | String |null
-------------
#### cryptoHandler
| 事件     | 说明 | 类型 | 默认值
| -------- | --- | --- | ---|
| filePath | 文件路径 | String |null
| cryptoType | 编码类型 | String |"SM3"加密 "Md5"编码值
-------------
### ExportUtil
#### listToExcel
| 事件     | 说明 | 类型 | 默认值
| -------- | --- | --- | ---|
| data | 传入数据 | List |null
| path | 路径 | String |null
| sheetName | 内部sheet名称 | String |sheet1 非必输
| fontSize | 字体大小 | String |10 非必输
| fontName | 字体名称 | String |宋体 非必输
| FontColor | 字体颜色 | String |RED、Black、Yellow三种 默认黑色 非必输
| backgroundColor | 背景颜色 | String |RED、Black、Yellow三种 默认无色 非必输
