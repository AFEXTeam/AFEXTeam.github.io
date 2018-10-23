# plugins的使用

## 1. Ajax
说明: 提供丰富的ajax操作方法，如get、post、delete等。
```js
//在main.js里面引入：
import Ajax from 'plugins/ajax'
Vue.use(ajax)

// 或者umd方式
// 引入构建的js文件
Vue.use(ajax)


//在组件里面调用
this.$http.get('http://httpbin.org/user-agent')
            .then(function (response) {
              console.log(response);
            })
            .catch(function (error) {
              console.log(error);
            });

```
**this.$http的原理:  Vue.prototype.$http = axios，因此具体使用方法参见 [axios仓库](www.baidu.com)**

## 2.Alert
说明: 对用户提供友好的信息提示
```js
//在main.js里面引入：
import  { Alert } from 'plugins/alert'
Vue.use(Alert)

// 或者umd方式
// 引入构建的js文件
Vue.use(Alert)


//在组件内部调用

// 显示
this.$aui.alert.show({
  title: 'aui is Cool',
  content: 'Do you agree?',
  buttonText: 'click me',
  onShow () {
    console.log('Plugin: I\'m showing')
  },
  onHide () {
    console.log('Plugin: I\'m hiding')
  }
})
// 隐藏
this.$aui.alert.hide()

```

<span class="aui-props-title">Props</span>
<p class="warning">
属性名请使用`小驼峰式`，比如`buttonText`而不是`button-text`。
</p>

| name   | type | default  |  version | description   |
|-------|-------|-------|-------|-------|
| <span class="prop-key" style="white-space:nowrap;">title</span> | <span class="type type-string">String</span> |  | <span style="font-size:12px;white-space:nowrap;"></span> | 弹窗标题 |
| <span class="prop-key" style="white-space:nowrap;">content</span> | <span class="type type-string">String</span> |  | <span style="font-size:12px;white-space:nowrap;">v2.2.0</span> | 提示内容，作为 slot:default 的默认内容，如果使用 slot:default, 将会失效 |
| <span class="prop-key" style="white-space:nowrap;">button-text</span> | <span class="type type-string">String</span> | ok(确定) | <span style="font-size:12px;white-space:nowrap;"></span> | 按钮文字 |
| <span class="prop-key" style="white-space:nowrap;">hide-on-blur</span> | <span class="type type-boolean">Boolean</span> | false | <span style="font-size:12px;white-space:nowrap;"></span> | 是否在点击遮罩时自动关闭弹窗 |
| <span class="prop-key" style="white-space:nowrap;">onShow</span> | <span class="type type-function">Function</span> |  | <span style="font-size:12px;white-space:nowrap;"></span> | 弹窗显示时触发的事件 |
| <span class="prop-key" style="white-space:nowrap;">onHide</span> | <span class="type type-function">Function</span> |  | <span style="font-size:12px;white-space:nowrap;"></span> | 弹窗关闭时触发的事件 |


<span class="aui-props-title">Events</span>

| name    | params   | description | version |
    |-------|-------|-------|-------|
| <span class="prop-key" style="white-space:nowrap;">show</span> |   &nbsp; | 显示弹窗 | <span style="font-size:12px;white-space:nowrap;"></span> |
| <span class="prop-key" style="white-space:nowrap;">hide</span> |   &nbsp; | 关闭弹窗 | <span style="font-size:12px;white-space:nowrap;"></span> |

## 3. Confirm
说明: 与用户产生良好的交互
```js
//在main.js里面引入：
import  Confirm from 'aui'
Vue.use(Confirm)

//组件内部调用

// 显示
const _this = this // 需要注意 onCancel 和 onConfirm 的 this 指向
this.$aui.confirm.show({
  // 组件除show外的属性
  showInput:true,
  onCancel () {
    console.log('cancel')
  },
  onShow(){
    // 设置输入值
    _this.$aui.confirm.setInputValue('value') // 注意需要在 onShow 事件中执行
  },
  onHide(){
    console.log('hide')
  }
})
// 隐藏
this.$aui.confirm.hide()
// prompt形式调用
this.$aui.confirm.prompt('placeholder', {
  onCancel () {},
  onConfirm () {}
})
```

<span class="aui-props-title">Props</span>
<p class="warning">
属性名请使用`小驼峰式`，比如`hideOnBlur`而不是`hide-on-blur`。
</p>

| name   | type | default  |  version | description   |
|-------|-------|-------|-------|-------|
| <span class="prop-key" style="white-space:nowrap;">show-input</span> | <span class="type type-boolean">Boolean</span> | false | <span style="font-size:12px;white-space:nowrap;">1.5.0</span> | 是否显示输入框，如果为true，slot会失效 |
| <span class="prop-key" style="white-space:nowrap;">placeholder</span> | <span class="type type-string">String</span> |  | <span style="font-size:12px;white-space:nowrap;">1.5.0</span> | 输入框的提示（仅在showInput为true的情况下有效） |
| <span class="prop-key" style="white-space:nowrap;">theme</span> | <span class="type type-string">String</span> | ios | <span style="font-size:12px;white-space:nowrap;"></span> | 弹窗风格，可以是ios或android |
| <span class="prop-key" style="white-space:nowrap;">hide-on-blur</span> | <span class="type type-boolean">Boolean</span> | false | <span style="font-size:12px;white-space:nowrap;"></span> | 是否在点击遮罩时自动关闭弹窗 |
| <span class="prop-key" style="white-space:nowrap;">title</span> | <span class="type type-string">String</span> |  | <span style="font-size:12px;white-space:nowrap;"></span> | 弹窗标题 |
| <span class="prop-key" style="white-space:nowrap;">content</span> | <span class="type type-string">String</span> |  | <span style="font-size:12px;white-space:nowrap;"></span> | 弹窗内容，作为slot默认内容，可以是html片段，如果使用slot该字段会失效 |
| <span class="prop-key" style="white-space:nowrap;">confirm-text</span> | <span class="type type-string">String</span> | 确认(confirm) | <span style="font-size:12px;white-space:nowrap;"></span> | 确认按钮的显示文字 |
| <span class="prop-key" style="white-space:nowrap;">cancel-text</span> | <span class="type type-string">String</span> | 取消(cancel) | <span style="font-size:12px;white-space:nowrap;"></span> | 取消按钮的显示文字 |
| <span class="prop-key" style="white-space:nowrap;">close-confirm</span> | <span class="type type-boolean">Boolean</span> | true | <span style="font-size:12px;white-space:nowrap;">1.5.0</span> | 是否在点击确认按钮时自动关闭 |
| <span class="prop-key" style="white-space:nowrap;">input-attrs</span> | <span class="type type-object">Object</span> |  | <span style="font-size:12px;white-space:nowrap;">v2.5.7</span> | input 属性 |
| <span class="prop-key" style="white-space:nowrap;">onCancel</span> |   <span class="type type-function">Function</span> |  | <span style="font-size:12px;white-space:nowrap;"></span> |点击取消按钮时触发事件|
| <span class="prop-key" style="white-space:nowrap;">onConfirm</span> |   <span class="type type-function">Function</span> |  | <span style="font-size:12px;white-space:nowrap;"></span> |点击确定按钮时触发事件, 参数为prompt中输入的值|
| <span class="prop-key" style="white-space:nowrap;">onShow</span> | <span class="type type-function">Function</span> |  | <span style="font-size:12px;white-space:nowrap;"></span> | 弹窗显示时触发的事件 |
| <span class="prop-key" style="white-space:nowrap;">onHide</span> | <span class="type type-function">Function</span> |  | <span style="font-size:12px;white-space:nowrap;"></span> | 弹窗关闭时触发的事件 |

<span class="aui-props-title">Events</span>

| name    | params   | description | version |
    |-------|-------|-------|-------|
| <span class="prop-key" style="white-space:nowrap;">show</span> |   &nbsp; | 弹窗出现时触发 | <span style="font-size:12px;white-space:nowrap;"></span> |
| <span class="prop-key" style="white-space:nowrap;">hide</span> |   &nbsp; | 弹窗隐藏时触发 | <span style="font-size:12px;white-space:nowrap;"></span> |
| <span class="prop-key" style="white-space:nowrap;">prompt</span> |   &nbsp; | 以prompt形式调用属性 | <span style="font-size:12px;white-space:nowrap;"></span> |

<span class="aui-props-title">Methods</span>

| name    | params   | description | version |
|-------|-------|-------|-------|
| <span class="prop-key" style="white-space:nowrap;">setInputValue</span> |   (value) | 设置输入值，当 show-input 为 true 时有效 |<span style="font-size:12px;white-space:nowrap;">v2.5.5</span> | 


## 4. Datetime
说明: 提供酷炫的日期选择器
```js
//在main.js里面引入： 
import Datetime from 'plugins/datetime'
Vue.use(Datetime)

// 组件内使用
this.$aui.datetime.show({
  value: '', // 其他参数同 props
  onHide () {
    const _this = this
  },
  onShow () {
    const _this = this
  }
})

this.$aui.datetime.hide()
```

<span class="aui-props-title">Props</span>
<p class="warning">
属性名请使用`小驼峰式`，比如`inlineDesc`而不是`inline-desc`。
</p>

| name   | type | default  |  version | description   |
|-------|-------|-------|-------|-------|
| <span class="prop-key" style="white-space:nowrap;">format</span> | <span class="type type-string">String</span> | YYYY-MM-DD | <span style="font-size:12px;white-space:nowrap;"></span> | 时间格式，不支持特殊字符，只能类似 YYYY-MM-DD HH:mm:ss 这样的格式 |
| <span class="prop-key" style="white-space:nowrap;">title</span> | <span class="type type-string">String</span> |  | <span style="font-size:12px;white-space:nowrap;"></span> | 标题 |
| <span class="prop-key" style="white-space:nowrap;">value</span> | <span class="type type-string">String</span> |  | <span style="font-size:12px;white-space:nowrap;"></span> | 表单值，`v-model`绑定 |
| <span class="prop-key" style="white-space:nowrap;">inline-desc</span> | <span class="type type-string">String</span> |  | <span style="font-size:12px;white-space:nowrap;"></span> | 描述字符 |
| <span class="prop-key" style="white-space:nowrap;">placeholder</span> | <span class="type type-string">String</span> |  | <span style="font-size:12px;white-space:nowrap;"></span> | 提示文字，当`value`为空时显示 |
| <span class="prop-key" style="white-space:nowrap;">min-year</span> | <span class="type type-number">Number</span> |  | <span style="font-size:12px;white-space:nowrap;"></span> | 可选择的最小年份 |
| <span class="prop-key" style="white-space:nowrap;">min-hour</span> | <span class="type type-number">Number</span> | 0 | <span style="font-size:12px;white-space:nowrap;"></span> | 限定小时最小值 |
| <span class="prop-key" style="white-space:nowrap;">max-hour</span> | <span class="type type-number">Number</span> | 23 | <span style="font-size:12px;white-space:nowrap;"></span> | 限定小时最大值 |
| <span class="prop-key" style="white-space:nowrap;">max-year</span> | <span class="type type-number">Number</span> |  | <span style="font-size:12px;white-space:nowrap;"></span> | 可选择的最大年份 |
| <span class="prop-key" style="white-space:nowrap;">confirm-text</span> | <span class="type type-string">String</span> | ok(确认) | <span style="font-size:12px;white-space:nowrap;"></span> | 确认按钮文字 |
| <span class="prop-key" style="white-space:nowrap;">cancel-text</span> | <span class="type type-string">String</span> | cancel(取消) | <span style="font-size:12px;white-space:nowrap;"></span> | 取消按钮文字 |
| <span class="prop-key" style="white-space:nowrap;">clear-text</span> | <span class="type type-string">String</span> |  | <span style="font-size:12px;white-space:nowrap;"></span> | 显示在中间的自定义按钮的文字 |
| <span class="prop-key" style="white-space:nowrap;">year-row</span> | <span class="type type-string">String</span> | {value} | <span style="font-size:12px;white-space:nowrap;"></span> | 年份的渲染模板 |
| <span class="prop-key" style="white-space:nowrap;">month-row</span> | <span class="type type-string">String</span> | {value} | <span style="font-size:12px;white-space:nowrap;"></span> | 月份的渲染模板 |
| <span class="prop-key" style="white-space:nowrap;">day-row</span> | <span class="type type-string">String</span> | {value} | <span style="font-size:12px;white-space:nowrap;"></span> | 日期的渲染模板 |
| <span class="prop-key" style="white-space:nowrap;">hour-row</span> | <span class="type type-string">String</span> | {value} | <span style="font-size:12px;white-space:nowrap;"></span> | 小时的渲染模板 |
| <span class="prop-key" style="white-space:nowrap;">minute-row</span> | <span class="type type-string">String</span> | {value} | <span style="font-size:12px;white-space:nowrap;"></span> | 分钟的渲染模板 |
| <span class="prop-key" style="white-space:nowrap;">start-date</span> | <span class="type type-string">String</span> |  | <span style="font-size:12px;white-space:nowrap;"></span> | 限定最小日期，格式必须为 YYYY-MM-DD，注意该限制只能限定到日期，不能限定到小时分钟。小时限定请使用`min-hour`和`max-hour` |
| <span class="prop-key" style="white-space:nowrap;">end-date</span> | <span class="type type-string">String</span> |  | <span style="font-size:12px;white-space:nowrap;"></span> | 限定最大日期，格式必须为 YYYY-MM-DD，注意该限制只能限定到日期，不能限定到小时分钟 |
| <span class="prop-key" style="white-space:nowrap;">required</span> | <span class="type type-boolean">Boolean</span> | false | <span style="font-size:12px;white-space:nowrap;"></span> | 是否必填 |
| <span class="prop-key" style="white-space:nowrap;">display-format</span> | <span class="type type-function">Function</span> |  | <span style="font-size:12px;white-space:nowrap;">v2.1.1-rc.11</span> | 自定义显示值 |
| <span class="prop-key" style="white-space:nowrap;">readonly</span> | <span class="type type-string">String</span> |  | <span style="font-size:12px;white-space:nowrap;">v2.3.6</span> | 只读模式，显示类似于 cell |
| <span class="prop-key" style="white-space:nowrap;">show</span> | <span class="type type-boolean">Boolean</span> |  | <span style="font-size:12px;white-space:nowrap;">v2.3.7</span> | 控制显示，要求 vue^2.3 |
| <span class="prop-key" style="white-space:nowrap;">minute-list</span> | <span class="type type-array">Array</span> |  | <span style="font-size:12px;white-space:nowrap;">v2.3.7</span> | 定义分钟列表，比如 ['00', '15', '30', '45'] |
| <span class="prop-key" style="white-space:nowrap;">hour-list</span> | <span class="type type-array">Array</span> |  | <span style="font-size:12px;white-space:nowrap;">v2.3.7</span> | 定义小时列表，比如 ['09', '10', '11', '12'] |
| <span class="prop-key" style="white-space:nowrap;">default-selected-value</span> | <span class="type type-string">String</span> |  | <span style="font-size:12px;white-space:nowrap;">v2.4.1</span> | 设置默认选中日期，当前 value 为空时有效 |
| <span class="prop-key" style="white-space:nowrap;">compute-hours-function</span> | <span class="type type-function">Function</span> |  | <span style="font-size:12px;white-space:nowrap;">v2.5.5</span> | 动态设置小时列表，参数为 `(value, isToday, generateRange)` |
| <span class="prop-key" style="white-space:nowrap;">compute-days-function</span> | <span class="type type-function">Function</span> |  | <span style="font-size:12px;white-space:nowrap;">v2.7.0</span> | 动态设置日期列表，参数为 `({year, month, min, max}, generateRange)` |
| <span class="prop-key" style="white-space:nowrap;">onShow</span> | <span class="type type-function">Function</span> |  | <span style="font-size:12px;white-space:nowrap;"></span> | 弹窗显示时触发的事件 |
| <span class="prop-key" style="white-space:nowrap;">onHide</span> | <span class="type type-function">Function</span> |  | <span style="font-size:12px;white-space:nowrap;"></span> | 弹窗关闭时触发的事件 |

<span class="aui-props-title">Events</span>

| name    | params   | description | version |
    |-------|-------|-------|-------|
| <span class="prop-key" style="white-space:nowrap;">change</span> |   `(value)` | 表单值变化时触发, 参数 `(newVal)` | <span style="font-size:12px;white-space:nowrap;"></span> |
| <span class="prop-key" style="white-space:nowrap;">clear</span> |   &nbsp; | 点击显示在中间的自定义按钮时触发 | <span style="font-size:12px;white-space:nowrap;"></span> |
| <span class="prop-key" style="white-space:nowrap;">show</span> |   &nbsp; | 弹窗显示时触发 | <span style="font-size:12px;white-space:nowrap;"></span> |
| <span class="prop-key" style="white-space:nowrap;">hide</span> |   `(type)`, type is one of [cancel, confirm] | 弹窗关闭时触发 | <span style="font-size:12px;white-space:nowrap;">v2.7.4</span> |
| <span class="prop-key" style="white-space:nowrap;">cancel</span> |   &nbsp; | 点击取消按钮或者遮罩时触发，等同于事件 hide(cancel) | <span style="font-size:12px;white-space:nowrap;">v2.7.4</span> |
| <span class="prop-key" style="white-space:nowrap;">confirm</span> |   &nbsp; | 点击确定按钮时触发，等同于事件 hide(confirm) | <span style="font-size:12px;white-space:nowrap;">v2.7.4</span> |

## 5. Loading
说明: 提供定制化的加载提示信息
```js
//在main.js里面引入：
import  Loading from 'plugins/loading'
Vue.use(Loading)

//在组件内部调用
// 显示
this.$aui.loading.show({
 text: 'Loading'
})
// 隐藏
this.$aui.loading.hide()
```
<p class="tip">
从v2.7.8版本开始以组件形式调用增加`delay`参数，从而实现延时显示.
</p>


<span class="aui-props-title">Props</span>

| name   | type | default  |  version | description   |
|-------|-------|-------|-------|-------|
| <span class="prop-key" style="white-space:nowrap;">show</span> | <span class="type type-boolean">Boolean</span> | false | <span style="font-size:12px;white-space:nowrap;"></span> | 显示状态，在 v2.5.7 前使用`v-model`绑定，后面直接使用 `:show` 绑定 |
| <span class="prop-key" style="white-space:nowrap;">text</span> | <span class="type type-string">String</span> |  | <span style="font-size:12px;white-space:nowrap;"></span> | 提示文字 |
| <span class="prop-key" style="white-space:nowrap;">position</span> | <span class="type type-string">String</span> | fixed | <span style="font-size:12px;white-space:nowrap;"></span> | 定位方式，默认为`fixed`，在100%的布局下用`absolute`可以避免抖动 |
| <span class="prop-key" style="white-space:nowrap;">transition</span> | <span class="type type-string">String</span> | aui-mask | <span style="font-size:12px;white-space:nowrap;"></span> | 显示动画名字 |

## 6. Toast
说明: 提供个性化的信息提示
```js
//在main.js里面引入：
import  Toast from 'aui'
Vue.use(Toast)

//组件内部调用
// 显示
this.$aui.toast.show({
 text: 'Loading'
})

// 显示文字
this.$aui.toast.text('hello', 'top')

// 隐藏
this.$aui.toast.hide()
```
<span class="aui-props-title">Props</span>
<p class="warning">
 属性名请使用`小驼峰式`，比如`isShowMask`而不是`is-show-mask`。
 </p>

| name   | type | default  |  version | description   |
|-------|-------|-------|-------|-------|
| <span class="prop-key" style="white-space:nowrap;">value</span> | <span class="type type-boolean">Boolean</span> | false | <span style="font-size:12px;white-space:nowrap;"></span> | 是否显示, 使用 v-model 绑定 |
| <span class="prop-key" style="white-space:nowrap;">time</span> | <span class="type type-number">Number</span> | 2000 | <span style="font-size:12px;white-space:nowrap;"></span> | 显示时间 |
| <span class="prop-key" style="white-space:nowrap;">type</span> | <span class="type type-string">String</span> | success | <span style="font-size:12px;white-space:nowrap;"></span> | 类型，可选值 success, warn, cancel, text |
| <span class="prop-key" style="white-space:nowrap;">width</span> | <span class="type type-string">String</span> | 7.6em | <span style="font-size:12px;white-space:nowrap;"></span> | 宽度 |
| <span class="prop-key" style="white-space:nowrap;">is-show-mask</span> | <span class="type type-boolean">Boolean</span> | false | <span style="font-size:12px;white-space:nowrap;"></span> | 是否显示遮罩，如果显示，用户将不能点击页面上其他元素 |
| <span class="prop-key" style="white-space:nowrap;">text</span> | <span class="type type-string">String</span> |  | <span style="font-size:12px;white-space:nowrap;"></span> | 提示内容，支持 html，和默认slot同样功能 |
| <span class="prop-key" style="white-space:nowrap;">position</span> | <span class="type type-string">String</span> | default | <span style="font-size:12px;white-space:nowrap;">v2.1.1-rc.4</span> | 显示位置，可选值 default, top, middle, bottom |


<span class="aui-props-title">Events</span>

| name    | params   | description | version |
    |-------|-------|-------|-------|
| <span class="prop-key" style="white-space:nowrap;">show</span> |   &nbsp; | 提示弹出时触发 | <span style="font-size:12px;white-space:nowrap;"></span> |
| <span class="prop-key" style="white-space:nowrap;">hide</span> |   &nbsp; | 提示隐藏时触发 | <span style="font-size:12px;white-space:nowrap;"></span> |