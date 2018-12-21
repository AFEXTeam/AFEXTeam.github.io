# ab-plugin-device-printer@打印配置项

1.引入

```js
import { Printer } from "./ab-plugin-device-printer";
```

2.事件方法的使用

> **解析aft文件**

### 详情请参考[打印文件(AFT)说明](https://github.com/AFEXTeam/AFEXTeam.github.io/blob/master/sdk-docs/sdk-docs/%E6%89%93%E5%8D%B0%E6%96%87%E4%BB%B6(AFT)%E8%AF%B4%E6%98%8E.docx "打印文件(AFT)说明")
#### parseAft
```js
    let path = "www/Test.aft";
    let map = {
      account: "1,230.00",
      text: "test",
      namelist:[{
        name:'hg',
        sexual:'male',
        age:'29'
        },{
        name:'ly',
        sexual:'famle',
        age:'18'
        }],
      huangguan:['123','456'],
      male:['nan','nv','other']
    };
    let controlParam = {
      notRepeatPrintHeaderFooter: "6,10"
    };
    let result = await Printer.parseAft(path, map, controlParam);
```


**Events promise函数**

|事件名|说明|参数|
|-----|:----:|:----:|
|parseAft|解析aft文件|path:String aft文件路径；mapping:Map 映射mapping；controlParam：Map 打印相关控制参数|

#### printPreviewXmlString
```js
    let xml = await Printer.parseAft(path, map, controlParam);
    let result = await Printer.printPreviewXmlString(xml);
```


**Events promise函数**

|事件名|说明|参数|
|-----|:----:|:----:|
|printPreviewXmlString|打印预览xmlString|xml:String xml字符串|
