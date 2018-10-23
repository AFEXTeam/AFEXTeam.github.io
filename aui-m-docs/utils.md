# utils的使用

## 1. filter过滤器
### 1.1 Array2stringFilter
#### 数组转换字符串过滤器   
说明:将一个数组的元素拼接成字符串,字符串之间用空格隔开
```js
//局部使用
// 引入 
import {Array2stringFilter} from '../../src/utils.js';
// 使用
{{[1,2]|Array2string}}

export default{
 data(){
   return {
     date: new Date()
   }
  },
 filters:{
  "Array2string": Array2stringFilter
}
} 
```
```js
//全局使用,在main.js引入
import {Array2stringFilter}  from '../src/utils'

Vue.filter("Array2string",Array2stringFilter)
//在组件中直接使用
{{[1,2]|Array2string}}
// 结果
"1 2"
```
### 1.2 FormatTimeFilter
#### 格式化时间过滤器  
说明:获取年月日星期时间，并格式化时间
参数说明:第一个参数data为时间,第二个参数默认为'YYYY-MM-DD HH:mm:ss'，可设置为'YYYY/MM/DD HH:mm:ss'
```js
// 在局部使用
// 引入
import {FormatTimeFilter} from '../../src/utils.js';
// 使用
{{date|formattime}}
export default{
 data(){
   return {
     date: new Date()
   }
  },
 filters:{
  "formattime": FormatTimeFilter
  }
} 
```
```js
//在全局中使用，在main.js中引入
import {FormatTimeFilter}  from '../src/utils'
Vue.filter("formattime",FormatTimeFilter)
//在组件中使用
{{date|formattime}}
```

### 1.3 FriendlyTimeFilter
#### 语义化时间过滤器  
说明:距离现在过去多长时间 功能是: 定义的时间和此刻的时间对比，在60s内为刚刚，在两分钟之内就是为1分钟之前，在一小时就是为具体多少分钟，在两个小时之内就是一个小时前，在一天之内就是具体多少小时前，等于一天，就是为昨天，超过一天小于7天就为多少天前，大于7天小于31天，就是为多少天前。
```js
//局部使用
// 引用
import {FriendlyTimeFilter} from '../../src/utils.js';
{{time|friendlytime}}
// 使用
export default {
  data(){
    return {
      time: '2018-2-28'
    }
  },
  fitlers:{
    "friendlytime":FriendlyTimeFilter
  }
}
// 结果
'1天前'

```

```js
//全局使用,在main.js中引入
import {FriendlyTimeFilter}  from '../src/utils'
Vue.filter("friendlytime",FriendlyTimeFilter)
// 在组件中使用
{{time|friendlytime}}
```

## 2. tools工具类
### 2.1 base64
#### 编码转码  
说明: base64.encode(String)将数据进行编码转换, base64.decode(String)将数据进行转码转换，还原成原来的数据
```js
// 组件中引入
import {base64} from '../../src/utils.js';
// 使用
var str = '我'
var strBase = base64.encode(str)

var strbsae = '5oiR'
var Str = base64.decode(strbsae)
// 结果
strBse:5oiR
Str:我
```
### 2.2 chinaMobile
#### 手机号码验证  
说明: 验证手机号码格式,返回的值为true或者false
```js
// 引入
import {chinaMobile} from '../../src/utils.js';
// 使用
var str = 17600237665
chinaMobile(str) 
// 结果
true
```
### 2.3 cookie
#### cookie存储  
说明: 设置浏览器的缓存cookie.get(),cookie.set(),cookie.remove()
```js
// 引入
import {cookie} from '../../src/utils.js';
// 使用
cookie.get(name, options) // 获取cookie
cookie.set(name, value, options) // 设置cookie
cookie.remove(name, options)  // 删除cookie
// 例如
cookie.set("MGT",360124,{}) //在浏览器中的cookie中就有了一段存储值
var a  = cookie.get("MGT",{}) 
a // 360124
cookie,remove("MGT",{}) //删除cookie中name为"MGT"的值
```
### 2.4 dateFormat
#### 时间格式化   
说明: 格式化时间,按照给定格式呈现
```js
// 引入
import {dateFormat} from '../../src/utils.js';

// 使用
var data = new Date()
dateFormat(data)
// 结果
'2018-4-10 16:30'
```
### 2.5 dateRange
#### 日期范围         
说明: 日期范围生成
```js
// 引入
import {dateRange} from '../../src/utils.js';

//调用
var start = new Date()
start.setFullYear(2018,3,9)
var end = new Date()  // 2018,4,10
dateRange(start,end)
// ["2018-04-09", "2018-04-10"]
```
### 2.6 debounce
#### 去抖      
说明: 强制一个函数在某个连续时间段内只执行一次,debounce函数接收两个参数,第一个是需要执行的callback回调函数,另一个是延迟的时间delay
```js
// 引入
import {debounce} from '../../src/utils.js';
// 使用
debounce(callback(),time)
// 例如
debounce(callback(),200)
function callback () {
  console.log("this debounce")
}
//强制200毫秒之内多次执行callback函数，只执行一次callback函数
```
### 2.7 md5
#### 加密解密        
说明: 对数据进行加密处理
```js
// 引入
import {md5} from '../../src/utils.js';
// 使用
var str = '我'
var strBase = md5(str)

var strbsae = '5oiR'
// 结果
strBse:16815254531798dc21ee979d1d9c6675
```

### 2.8 numberComma
#### 数字格式化      
说明: 将数字类型进行格式化(默认每三位加一个逗号分隔) 
参数说明: source需要格式化的数据,index每个多少位加一个逗号分隔
```js
// 引入 
import {numberComma} from '../../src/utils.js';

numberComma(source,index)
// 使用
var source = 187678.11
console.log(numberComma(source, 2))
// 结果
'18,76,78.11'
```
### 2.9 numberPad 
#### 数字补位    
说明: 如果数字是个位数，那么在处理之后在他之前补'0'
```js
// 引入 
import {numberPad} from '../../src/utils.js';

// 使用
console.log(numberPad(2))
// 结果
02
```
###  2.10 numberRandom
#### 随机数        
说明: 在给定范围内进行生成一个随机数, 这个随机数是start到end的随机整数
```js
// 引入
import {numberRandom} from '../../src/utils.js';
// 使用
console.log(numberRandom(2, 5))
// 结果
3
```
### 2.11 numberRange
#### 一个范围数字格式化        
说明:在给定范围内生成一个数组，这个数组包含从start到end之间的的整数元素                   
参数说明: start为开始元素,end为结束元素,第三个参数boolean默认为false,显示为从start到end之间的整数元素组成的数组, boolean为true,则在数字前补"0",整数字符元素组成的数组
```js
// 引入
import {numberRange} from '../../src/utils.js';

numberRange(start,end,boolean)
// 使用 
numberRange(-1,2,true)
// 结果
["-01", "00", "01", "02"]
// 使用
numberRange(-1,2)
// 结果
[-1, 0, 1, 2]
```
### 2.12 querystring
#### 编码和解码,数据类型转换
说明:字符串的编码和解码,并且对数据类型的转换。
```js
// 引入
import querystring from '../../src/utils.js';

// 使用
//  querystring.escape() 对字符串进行编码
querystring.escape("zan tong")  // 对空格进行编码
// zan%20tong

// querystring.unescape() 对 querystring.escape() 编码的字符串进行解码
querystring.unescape("zan%20tong")  //使用 unescape() 对 escape() 编码的字符串进行解码
// zan tong

//querystring.stringify(obj) 对象形式解析成字符串形式
querystring.stringify({"zantong":"赞同"})
// zantong = 赞同 对象形式解析成字符串形式

//querystring.parse(string) 字符串形式解析成对象形式
querystring.parse("mgt")
// {mgt: ""} 解析成对象形式
```
### 2.13 trim
#### 删除字符串收尾空格
说明:去掉字符序列左边和右边的空格
```js
//  引入
import {trim} from '../../src/utils.js';
// 使用
trim(" zantong ")
// "zantong"
```
### 2.14 throttle
#### 节流        
说明:  创建并返回一个像节流阀一样的函数，当重复调用函数的时候，最多每隔 wait毫秒调用一次该函数
```js
// 引入
import {throttle} from '../../src/utils.js';
// 使用
throttle(callback(),time)
// 例如
throttle(callback(),200)
function callback () {
  console.log("this throttle")
};

```

### 2.15 ChinaAddressData
#### 中国省份数据      
说明:获取中国省份Json数据
```js
// 引入
  import {ChinaAddressData} from '../../src/utils.js';
// 使用
  console.log(ChinaAddressData) 
  // 为各县市级的信息
  [
    [{name:"北京市",value:"110000"},{},...],
    ...
  ]
```
### 2.16 name2value
#### name转化为value工具 
说明:将name转化为key值,实现数据的转换
```js
// 在局部中使用
// 引入
import {name2value} from '../../src/utils.js';
// 使用
export default {
  data(){
    return {
      name: "北京市",
      list [
        {'北京市':'110100'},
        {'天津市':'120100'},
        {'上海市': '310100'},
        {'重庆市': '500100'}
      ]   
    }
  },
 mounted() {
    name2value(this.name, this.list)
  }
}
// 结果
'110100'
```
### 2.17 value2name
#### value转化为name工具  
说明: 通过key值转化为name值，实现数据转换
```js
// 引入
import {value2name} from '../../src/utils.js';

// 使用
export default {
  data(){
    return {
      name: '朝阳区',
      list :[["朝"],["阳"],["区"]]
    }
  },
 mounted() {
    console.log(value2name(this.name, this.list))
  }
}
```

