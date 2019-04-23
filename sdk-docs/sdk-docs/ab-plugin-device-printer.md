# ab-plugin-device-printer@打印配置项

1.引入

```js
import { Printer } from "./ab-plugin-device-printer";
```

2.事件方法的使用

> **解析aft文件**

### 详情请参考[打印文件(AFT)说明](https://github.com/AFEXTeam/AFEXTeam.github.io/blob/master/sdk-docs/sdk-docs/%E6%89%93%E5%8D%B0%E6%96%87%E4%BB%B6(AFT)%E8%AF%B4%E6%98%8E.docx)
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

#### parseMultiPageAft
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
    let result = await Printer.parseMultiPageAft(path, map, controlParam);
```

#### combineAndClipAft

|事件名|说明|参数|
|-----|:----:|:----:|
|parseAft|解析aft文件|gaps:list 合并时每页面之间域的间距List；insertElemMarginTop:String   MapinsertXml插入新页时距离顶部的偏移量；insertElemMarginBottom：String insertXml插入新页时底部距离下一field的偏移量,insertXml为空时可视作页面顶部偏移量;insertXml:String 每次换页时在头部插入的aft Xml String,可以为null;clipThreshold:String 切割限制,合并时位置超出此高度的域会被加入下页|
```js
    let xml = await Printer.parseAft(path, map, controlParam);
    let result = await Printer.combineAndClipAft(xml,gaps,insertElemMarginTop,insertElemMarginBottom,insertXml,clipThreshold);
```

#### aftToPdf
```js
    let result = await Printer.aftToPdf(aftPath, pdfPath, mapping, controlParams,waterMarkName,font);
```


**Events promise函数**

|事件名|说明|参数|
|-----|:----:|:----:|
|aftToPdf|aft转换为pdf|aftPath:String aft文件路径；pdfPath:String pdf文件路径；mapping 所有文本框的赋值；controlParams Map<String, Object>；waterMarkName:String 水印值；font 水印字体大小|

#### looperAftToPdf
```js
    let result = await Printer.looperAftToPdf(aftPath, pdfPath, jointString,mapping, controlParams,waterMarkName,font);
```


**Events promise函数**

|事件名|说明|参数|
|-----|:----:|:----:|
|looperAftToPdf|循环打印PDF|aftPath:String aft文件路径；pdfPath:String pdf文件路径；jointString 一页中aft的数量；mapping 所有文本框的赋值；controlParams Map<String, Object>；waterMarkName:String 水印值；font 水印字体大小|

#### selectDirector
```js
    let result = await Printer.selectDirector(mkdirOrGet);
```


**Events promise函数**

|事件名|说明|参数|
|-----|:----:|:----:|
|selectDirector|选择文件夹目录|mkdirOrGet:String 文件夹目录判断常量|

#### concatAft
```js
    let result = await Printer.concatAft(aftList,pdfString,mapping,controlParams,waterMarkName,font);
```


**Events promise函数**

|事件名|说明|参数|
|-----|:----:|:----:|
|concatAft|合并aft|aftList:List<String> 所有aft文件路径；pdfPath:String pdf文件路径；mapping 所有文本框的赋值；controlParams Map<String, Object>；waterMarkName:String 水印值；font 水印字体大小|

#### looperAddPicture
```js
    let result = await Printer.looperAddPicture(aftPath, pdfPath, mapping, controlParams,waterMarkName,font);
```


**Events promise函数**

|事件名|说明|参数|
|-----|:----:|:----:|
|looperAddPicture|AFT中按需求添加图片|aftPath aft文件路径；pdfPath:String pdf文件路径；mapping 所有文本框的赋值；ImgSrcKey 图片src的值；controlParams Map<String, Object>；waterMarkName:String 水印值；font 水印字体大小|


#### printTableWithLine
```js
    let path = "www/table.aft";
      let map = {
        TranNm: "我是表头!",
        _printDate_: "打印时间！",
        BrahNum: "打印机构！",
        PRT_CZY: "操作员",
        PRT_SQY: "授权员",
        PRT_FHY: "复核员"
      };
      let data = [
        ["第一行第一列", "第一行第二列","第一行第三列","第一行第四列"],
        ["第二行第一列", "第二行第二列"]
      ];
      let colWidth = 50;
      let controlParam = {
        TableColWidth: "true"
      };

      let result = await Printer.printTableWithLine(
        path,
        map,
        data,
        colWidth,
        controlParam
      );
```


**Events promise函数**

|事件名|说明|参数|
|-----|:----:|:----:|
|printTableWithLine|通用表格打印（带线）|{String} aftPath 通用aft路径，{Map} mapping 数据映射关系，{List<List<String>>} data 表格数据，{int} colWidth 单元格宽度，{Map} controlParams 配置参数|
