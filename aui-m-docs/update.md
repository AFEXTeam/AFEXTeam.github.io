## <a class="aui-demo-link" href="#" router-link="./demos/aui-button">aui-button(按钮)</a>
### Attribute：
1. action-type 修改成 native-type
2. show-loading 修改成 loading

|  参数     | 说明     | 类型      | 可选值        | 默认值   |
|---------- |-------- |---------- |------------- |--------  |
|**native-type**|button原生 type 属性|string|**submit**/**button**/**reset**|**submit**|
|**loading**|是否显示加载中状态图标|boolean|--|**false**|

## <a class="aui-demo-link" href="#" router-link="./demos/aui-switch">aui-switch (开关)</a>
### Attribute：
1. title 修改为非必要输入

|  参数     | 说明     | 类型      | 可选值        | 默认值   |
|---------- |-------- |---------- |------------- |--------  |
|**title**|label文字|string|--|--|

### Event:
1. on-click 修改为 click
2. on-change 修改为  change

|  函数名     | 参数     | 说明      | 
|---------- |-------- |---------- |
|**click**|(newVal, oldVal)|点击组件时触发|
|**change**|(value)|值变化时触发，参数为 (currentValue|

## <a class="aui-demo-link" href="#" router-link="./demos/aui-input-number">aui-input-number (计数器)</a>
### Component：
1.**aui-number** 修改 **aui-input-number**

## <a class="aui-demo-link" href="#" router-link="./demos/swiper">swiper (轮播图)</a>
### Attribute：
1. **auto** 修改为 **autoplay**

|  参数     | 说明     | 类型      | 可选值        | 默认值   |
|---------- |-------- |---------- |------------- |--------  |
|**autoplay**|是否自动轮播|Boolean|--|false|

### Event：
1. **on-index-change** 修改为 **index-change**
2. **on-get-height** 修改为 **get-height**
3. **on-click-list-item** 修改为 **click-list-item**

|  函数名     | 参数     | 说明      | 版本 |
|---------- |-------- |---------- |---------- |
|**index-change**|(currentIndex)|轮播 index 变化时触发|--|
|**get-height**|(height)|高度获取后触发|v2.7.0|
|**click-list-item**|--|--|--|


## <a class="aui-demo-link" href="#" router-link="./demos/badge">badge</a>
### Attribute：
1. **text** 修改成 **value**
2. 增加 **max** 最大数值属性

|  参数     | 说明     | 类型      | 可选值        | 默认值   |
|---------- |-------- |---------- |------------- |--------  |
|**text**|显示的文字|string|--|--|
|**max**|超过max时显示{{max}}|--|--|--|
|number|--|--|--|--|

## <a class="aui-demo-link" href="#" router-link="./demos/confirm">aui-confirm (消息提示框)</a>
### Attribute：
1. **message** 修改成 **content**

|  参数     | 说明     | 类型      | 可选值        | 默认值   |
|---------- |-------- |---------- |------------- |--------  |
|**content**|弹出框显示的内容|string|--|--|

### Event:
1. **on-confirm** 修改为 **confirm**

|  函数名     | 参数     | 说明      | 
|---------- |-------- |---------- |
|**confirm**|(value)|点击确定按钮时触发, 参数为prompt中输入的值|



## <a class="aui-demo-link" href="#" router-link="./demos/aui-dialog">aui-dialog (弹窗)</a>
### Event：
1. **on-show** 修改成 **show**
2. **on-hide** 修改成 **hide**
3. **on-click-mask** 修改成 **click-mask**

|  函数名     | 参数     | 说明      | 
|---------- |-------- |---------- |
|**show**|--|弹窗可见时触发|
|**hide**|--|弹窗关闭时触发|
|**click-mask**|--|--|



## <a class="aui-demo-link" href="#" router-link="./demos/card">card </a>
### Attribute：
1. 增加 **bodyStyle** 内容格式

|  参数     | 说明     | 类型      | 可选值        | 默认值   |
|---------- |-------- |---------- |------------- |--------  |
|**bodyStyle**|卡片的样式|object|--| { padding: '20px' }

### Event:
1. **on-click-header** 修改为 **click-header**
2. **on-click-footer** 修改为 **click-footer**

|  函数名    | 参数    | 说明 |版本|
|---------- |-------- |-------  |-------  |
|**click-header**|--|点击头部时触发|--|
|**click-footer**|--|点击底部时触发|--|



## <a class="aui-demo-link" href="#" router-link="./demos/rate">rate </a>
### Component：
1. **aui-rates** 修改为 **aui-rate**


## <a class='aui-demo-link' href="#" router-link='./demos/aui-header'>aui-header</a>
### Attribute:
1. **right** 修改成 **rightHtml**

| 参数    | 说明   | 类型    | 可选值      | 默认值      |
|---------- |-------- |---------- |------------- |--------  |
|**rightHtml**|header右侧显示的文本内容，如果showMore存在则不显示|string|--|false|

### event:
1. **on-click-more** 修改成 **click-more**
2. **on-click-back** 修改成 **click-back**
3. **on-click-title** 修改成 **click-title**

|  函数名    | 参数    | 说明 |
|---------- |-------- |-------|
|**click-more**|--|点击右侧更多时触发|
|**click-back**|--|当left-options.preventGoBack为true,点击左边返回时触发|
|**click-title**|--|点击标题时触发|



## <a class="aui-demo-link" href="#" router-link="./demos/cell">cell </a>
### Attribute:
1. **cellicon** 修改成 **cellBadgeText**

|  参数     | 说明     | 类型      | 可选值        | 默认值   |
|---------- |-------- |---------- |------------- |--------  |
|**cellBadgeText**|显示badge徽章，badge中的内容|string|--|--|



## <a class="aui-demo-link" href="#" router-link="./demos/masker">masker </a>
### Attribute:
1. 新增 **content**

|  参数     | 说明     | 类型      | 可选值        | 默认值   |
|---------- |-------- |---------- |------------- |--------  |
|**content**|遮罩上方内容，一般显示标题消息,content插槽不存在时有效|string|--|--|



## <a class="aui-demo-link" href="#" router-link="./demos/swipeout">swipeout </a>
### Attribute:
1. 新增 **rightMenu**
2. 新增 **leftMenu**

|  参数     | 说明     | 类型      | 可选值        | 默认值   |
|---------- |-------- |---------- |------------- |--------  |
|**rightMenu**|undefined|string|--|--|
|**leftMenu**|undefined|string|--|--|

### Event:
1. **on-close** 修改为 **close**
2. **on-open** 修改为 **open**

|  函数名    | 参数    | 说明 |
|---------- |-------- |-------  |
|**close**|--|菜单完全关闭时触发|
|**open**|--|菜单完全打开时触发|


## <a class="aui-demo-link" href="#" router-link="./demos/tabber">tabber </a>
### Attribute:
1. 新增 **icon**
2. 新增 **icon-active**

|  参数     | 说明     | 版本   |
|---------- |-------- |--------  |
|**icon**|图标区域|--|
|**icon-active**|如果存在，当前 tabbar-item 点击时会显示，用于切换图标|v2.1.1-rc.8|

### Event:
1. **on-index-change** 修改为 **index-change**

|  函数名    | 参数    | 说明 | 版本 |
|---------- |-------- |-------  | --|
|**index-change**|--|value 值变化时触发|v2.5.4|



## <a class="aui-demo-link" href="#" router-link="./demos/aui-input">aui-input </a>
### Event:
1.  **on-change** 修改为 **change**
2.  **on-focus** 修改为 **focus**
3.  **on-blur** 修改为 **blur**
4.  **on-enter** 修改为 **enter**
5.  **on-click-error-icon** 修改为 **click-error-icon**

|  函数名    | 参数    | 说明 |
|---------- |-------- |-------  |
|**change**|(value, $event)|输入值变化时触发。如果你使用了debounce，那么触发将不会是实时的。|
|**focus**|(value, $event)| 手动获得焦点|
|**blur**|(value, $event)| 手动设置 input 失去焦点|
|**enter**|(value, $event)| input输入完成后点击enter(确认)事件 |
|**click-error-icon**|(error)| 点击错误图标时触发，你可以关闭 should-toast-error 然后用这个事件来自定义显示错误的提示内容 |



## <a class="aui-demo-link" href="#" router-link="./demos/aui-input-number">aui-input-number </a>
### Event:
1.  **on-change** 修改为 **change**

|  函数名    | 参数    | 说明 |
|---------- |-------- |-------  |
|**change**|--|--|



## <a class="aui-demo-link" href="#" router-link="./demos/calendar">calendar </a>
### Event:
1.  **on-change** 修改为 **change**
2.  **on-show** 修改为 **show**
3.  **on-hide** 修改为 **hide**

|  函数名    | 参数    | 说明 |
|---------- |-------- |-------  |
|**change**|(value)|值改变时触发|
|**show**|--|弹窗显示时触发|
|**hide**|--|弹窗关闭时触发|



## <a class="aui-demo-link" href="#" router-link="./demos/checklist">checklist </a>
### Event:
1.  **on-change** 修改为 **change**
2.  **on-error** 修改为 **error**

|  函数名    | 参数    | 说明 |
|---------- |-------- |-------  |
|**change**|(value, label)|值变化时触发，参数为 (value, label)，其中label参数在v2.5.7后支持|
|**error**|--|--|



## <a class="aui-demo-link" href="#" router-link="./demos/datetime">datetime </a>
### Event:
1.  **on-change** 修改为 **change**
2.  **on-show** 修改为 **show**
3.  **on-hide** 修改为 **hide**
4.  **on-cancel** 修改为 **cancel**
5.  **on-confirm** 修改为 **confirm**
5.  **on-clear** 修改为 **clear**

|  函数名    | 参数    | 说明 |版本|
|---------- |-------- |-------  |-------  |
|**change**|(value)|表单值变化时触发, 参数 (newVal)|--|
|**show**|--|弹窗显示时触发|--|
|**hide**|--|弹窗关闭时触发|--|
|**cancel**|--|点击取消按钮或者遮罩时触发，等同于事件 on-hide(cancel)|v2.7.4 |
|**confirm**|--|点击确定按钮时触发，等同于事件 on-hide(confirm)|v2.7.4 |
|**clear**|--|点击显示在中间的自定义按钮时触发|-- |


## <a class="aui-demo-link" href="#" router-link="./demos/datetime-range">datetime-range </a>
### Event:
1.  **on-change** 修改为 **change**

|  函数名    | 参数    | 说明 |
|---------- |-------- |-------  |
|**change**|--|--|




## <a class="aui-demo-link" href="#" router-link="./demos/inline-calendar">inline-calendar </a>
### Event:
1.  **on-change** 修改为 **change**
2.  **on-select-single-date** 修改为 **select-single-date**
3.  **on-view-change** 修改为 **view-change**

|  函数名    | 参数    | 说明 | 版本 |
|---------- |-------- |-------  |----|
|**change**|--|值变化时触发|--|
|**select-single-date**|(currentValue)|单选模式下选中日期时触发|2.7.6|
|**view-change**|(data, index)|渲染月份变化时触发。初始化时会触发一次，如果不希望处理初始化时的触发，可以检查第二个参数是否为 0|v2.5.12|



## <a class="aui-demo-link" href="#" router-link="./demos/picker">picker </a>
### Event:
1.  **on-change** 修改为 **change**

|  函数名    | 参数    | 说明 |
|---------- |-------- |-------  |
|**change**|(value)|选择值变化时触发|




## <a class="aui-demo-link" href="#" router-link="./demos/popup-picker">popup-picker </a>
### Event:
1.  **on-change** 修改为 **change**
2.  **on-show** 修改为 **show**
3.  **on-hide** 修改为 **hide**
4.  **on-shadow-change** 修改为 **shadow-change**

|  函数名    | 参数    | 说明 |版本 |
|---------- |-------- |-------  |----|
|**change**|(value)|值变化时触发|--|
|**show**|--|弹窗出现时触发|--|
|**hide**|--|(closeType) true表示confirm(选择确认), false表示其他情况的关闭|弹窗关闭时触发|--|
|**shadow-change**|(Array ids, Array names)|picker 值变化时触发，即滑动 picker 时触发|v2.5.6|



## <a class="aui-demo-link" href="#" router-link="./demos/popup-radio">popup-radio </a>
### Event:
1.  **on-change** 修改为 **change**
2.  **on-show** 修改为 **show**
3.  **on-hide** 修改为 **hide**

|  函数名    | 参数    | 说明 | 版本 |
|---------- |-------- |-------  |---|
|**change**|(value)|值变化时触发|--|
|**show**|--|弹窗出现时触发|v2.6.5|
|**hide**|--|弹窗关闭时触发|v2.6.5|




## <a class="aui-demo-link" href="#" router-link="./demos/aui-textarea">aui-textarea</a>
### Event:
1.  **on-change** 修改为 **change**
2.  **on-focus** 修改为 **focus**
3.  **on-blur** 修改为 **blur**

|  函数名    | 参数    | 说明 | 版本 |
|---------- |-------- |-------  |--|
|**change**|(value)|表单值变化时触发|--|
|**focus**|--|focus 事件|v2.1.1-rc.11|
|**focus**|--|blur 事件|v2.1.1-rc.11|



## <a class="aui-demo-link" href="#" router-link="./demos/checker">checker</a>
### Event:
1.  **on-change** 修改为 **change**
2. **on-item-click** 修改为 **item-click**

|  函数名    | 参数    | 说明 |
|---------- |-------- |-------  |
|**change**|(value)|value值变化时触发|
|**item-click**|(itemValue, itemDisabled)|当前项被点击时触发|



## <a class="aui-demo-link" href="#" router-link="./demos/range">range</a>
### Event:
1.  **on-change** 修改为 **change**

|  函数名    | 参数    | 说明 |版本 |
|---------- |-------- |-------  |-------  |
|**change**|(value)|绑定值变化时触发事件|v2.2.2|



## <a class="aui-demo-link" href="#" router-link="./demos/search">search</a>
### Event:
1.  **on-change** 修改为 **change**
2.  **on-blur** 修改为 **blur**
3.  **on-cancel** 修改为 **cancel**
4.  **on-submit** 修改为 **submit**
5.  **on-result-click** 修改为 **result-click**
6.  **on-touch** 修改为 **touch**

|  函数名    | 参数    | 说明 |版本 |
|---------- |-------- |-------  |--|
|**change**|(value)|输入文字变化时触发|--|
|**blur**|--|输入框失去焦点时触发|v2.6.3|
|**cancel**|--|点击取消按钮时触发|--|
|**submit**|(value)|表单提交时触发|--|
|**result-click**|(item)|点击结果条目时触发|--|



## <a class="aui-demo-link" href="#" router-link="./demos/selector">selector</a>
### Event:
1.  **on-change** 修改为 **change**

|  函数名    | 参数    | 说明 |
|---------- |-------- |-------|
|**change**|(value)|值变化时触发|



## <a class="aui-demo-link" href="#" router-link="./demos/alert">alert</a>
### Event:
1.  **on-show** 修改为 **show**
2.  **on-hide** 修改为 **hide**

|  函数名    | 参数    | 说明 |
|---------- |-------- |-------|
|**show**|--|显示时触发|
|**hide**|--|关闭后触发，当非确定时，参数为false，反之为true|


## <a class="aui-demo-link" href="#" router-link="./demos/aui-address">aui-address</a>
### Event:
1.  **on-show** 修改为 **show**
2.  **on-hide** 修改为 **hide**
3.  **on-shadow-change** 修改为 **shadow-change**

|  函数名    | 参数    | 说明 | 版本 |
|---------- |-------- |-------|----|
|**show**|--|显示时触发|--|
|**hide**|--|关闭后触发，当非确定时，参数为false，反之为true|--|
|**shadow-change**|(Array ids, Array names)|picker 值变化时触发，即滑动 picker 时触发|v2.6.3|


## <a class="aui-demo-link" href="#" router-link="./demos/confirm">confirm</a>
### Event:
1.  **on-show** 修改为 **show**
2.  **on-hide** 修改为 **hide**
3. **on-cancel** 修改为 **cancel**

|  函数名    | 参数    | 说明 |
|---------- |-------- |-------|
|**show**|--|弹窗出现时触发|
|**hide**|--|弹窗隐藏时触发|
|**cancel**|(value)|点击确定按钮时触发, 参数为prompt中输入的值|



## <a class="aui-demo-link" href="#" router-link="./demos/drawer">drawer</a>
### Event:
1.  **on-show** 修改为 **show**
2.  **on-hide** 修改为 **hide**

|  函数名    | 参数    | 说明 |
|---------- |-------- |-------|
|**show**|--|--|
|**hide**|--|--|




## <a class="aui-demo-link" href="#" router-link="./demos/popover">popover</a>
### Event:
1.  **on-show** 修改为 **show**
2.  **on-hide** 修改为 **hide**
3.  **on-click-content** 修改为 **click-content**

|  函数名    | 参数    | 说明 |
|---------- |-------- |-------|
|**show**|--|弹窗显示时触发|
|**hide**|--|弹窗关闭时触发|




## <a class="aui-demo-link" href="#" router-link="./demos/popup">popup</a>
### Event:
1.  **on-show** 修改为 **show**
2.  **on-hide** 修改为 **hide**
3.  **on-first-show** 修改为 **first-show**

|  函数名    | 参数    | 说明 |
|---------- |-------- |-------|
|**show**|--|显示时触发|
|**hide**|--|关闭时触发|
|**first-show**|--|第一次显示时触发，可以在该事件回调里初始化数据或者界面|



## <a class="aui-demo-link" href="#" router-link="./demos/toast">toast</a>
### Event:
1.  **on-show** 修改为 **show**
2.  **on-hide** 修改为 **hide**

|  函数名    | 参数    | 说明 |
|---------- |-------- |-------|
|**show**|--|提示弹出时触发|
|**hide**|--|提示隐藏时触发|



## <a class="aui-demo-link" href="#" router-link="./demos/actionsheet">actionsheet</a>
### Event: 
1. **on-click-menu** 修改为 **click-menu** 
2. **on-click-mask** 修改为 **click-mask**

|  函数名    | 参数    | 说明 |版本 |
|---------- |-------- |-------|-- |
|**click-menu**|(menuKey, menuItem)|点击菜单时触发|--|
|**click-mask**|--|点击遮罩时触发|v2.3.4|



## <a class="aui-demo-link" href="#" router-link="./demos/aui-img">aui-img</a>
### Event: 
1. **on-success** 修改为 **success** 

|  函数名    | 参数    | 说明 |版本 |
|---------- |-------- |-------|-- |
|**success**|--|--|--|



## <a class="aui-demo-link" href="#" router-link="./demos/button-tab">button-tab</a>
### Event: 
1. **on-item-click** 修改为 **item-click**

|  函数名    | 参数    | 说明 |版本 |
|---------- |-------- |-------|-- |
|**item-click**|(index)|当前按钮点击时触发|--|



## <a class="aui-demo-link" href="#" router-link="./demos/tab">tab</a>
### Event: 
1. **on-item-click** 修改为 **item-click**
2. **on-index-change** 修改为 **index-change**
3. **on-before-index-change** 修改为 **before-index-change**

|  函数名    | 参数    | 说明 |版本 |
|---------- |-------- |-------|-- |
|**item-click**|(index)|当前 tabItem 被点击时触发|v2.2.1-rc.4|
|**index-change**|(index)|当前 tabItem 被点击时触发|v2.2.1-rc.4|



## <a class="aui-demo-link" href="#" router-link="./demos/popup-header">popup-header</a>
### Event: 
1. **on-click-left** 修改为 **click-left**
2. **on-click-right** 修改为 **click-right**

|  函数名    | 参数    | 说明 |版本 |
|---------- |-------- |-------|-- |
|**click-left**|--|左侧文字点击时触发|v2.5.2|
|**click-right**|--|右侧文字点击时触发|v2.5.2|



## <a class="aui-demo-link" href="#" router-link="./demos/panel">panel</a>
### Event:
1. **on-click-header** 修改为 **click-header**
2. **on-click-footer** 修改为 **click-footer**

|  函数名    | 参数    | 说明 |版本|
|---------- |-------- |-------  |-------  |
|**click-header**|--|点击头部时触发|--|
|**click-footer**|--|点击底部时触发|--|



## <a class="aui-demo-link" href="#" router-link="./demos/clocker">clocker</a>
### Event:
1. **on-tick** 修改为 **tick**
1. **on-click-item** 修改为 **click-item**
1. **on-img-error** 修改为 **img-error**

|  函数名    | 参数    | 说明 |版本|
|---------- |-------- |-------  |-------  |
|**tick**|--|时间计算时触发，但非精确每1s触发|--|
|**click-item**|--|时间计算时触发，但非精确每1s触发|--|
|**img-error**|--|时间计算时触发，但非精确每1s触发|--|



## <a class="aui-demo-link" href="#" router-link="./demos/previewer">previewer</a>
### Event:
1. **on-close** 修改为 **close**

|  函数名    | 参数    | 说明 |版本|
|---------- |-------- |-------  |-------  |
|**close**|--|关闭时触发|v2.2.1-rc.4|



## <a class="aui-demo-link" href="#" router-link="./demos/shake">shake</a>
### Method:
1. **on-shake** 修改为 **shake**

|  方法名    | 参数    | 说明 |版本|
|---------- |-------- |-------  |-------  |
|**shake**|--|关闭时触发|v2.2.1-rc.4|



## <a class="aui-demo-link" href="#" router-link="./demos/scroller">scroller</a>
### Event:
1. **on-scroll** 修改为 **scroll**
2. **on-scroll-bottom**  修改为 **scroll-bottom**
3. **on-pulldown-loading**  修改为 **pulldown-loading**
4. **on-pullup-loading**  修改为 **pullup-loading**

|  函数名    | 参数    | 说明 |版本|
|---------- |-------- |-------  |-------  |
|**scroll**|(position)|容器滚动时触发，参数为top和left位置|--|
|**scroll-bottom**|--|滚动到底部时触发，注意事件会触发多次，如果你需要进行数据获取，记得设置一个状态值|v2.2.1-rc.6|
|**pulldown-loading**|--|用户触发下拉刷新状态，监听该事件以获取加载新数据|--|
|**pullup-loading**|--|用户触发上拉加载状态，监听该事件以加载新数据|--|
