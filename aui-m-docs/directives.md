## directive指令
```js
全局引入指令时，在main.js添加下列代码
//使用指令
import {ClickOutsideDirective,InviewDirective, TransferDomDirective} from './utils.js';
Vue.directive('click-outside', ClickOutsideDirective)
Vue.directive('transfer-dom', TransferDomDirective)

```

### 1 ClickOutsideDirective
#### 点击区域外的指令        
说明: 点击区域外触发的事件
```js
// main.js 全局注册v-click-outside指令
import {ClickOutsideDirective} from './utils'
Vue.directive('click-outside', ClickOutsideDirective)
```
```html
<div v-click-outside="onClickedOutside"></div>
```
```js
onClickedOutside(){
  console.log("点击区域外触发")
}
```
在局部组件中使用
```html
<div v-click-outside="onClickedOutside"></div>
```
```js
import {ClickOutsideDirective} from '../../src/utils.js';
  directives:{
     "click-outside": ClickOutsideDirective
  },
  methods:{
    onClickedOutside(){
      console.log("点击区域外触发")
    }
  }
```

### 2 TransferDomDirective
说明: 不重复渲染元素

```js
// main.js 全局注册指令v-transfer-dom
import {TransferDomDirective} from './utils'
Vue.directive('transfer-dom', TransferDomDirective)
```
```html
<div v-transfer-dom></div>
```


在局部组件中使用
```html
<div v-transferdom></div>
```
```js
import {TransferDomDirective} from '../../src/utils.js';
  directives:{
     "transferdom": TransferDomDirective
  }
```