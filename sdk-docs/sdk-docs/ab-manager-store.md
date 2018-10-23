# ab-manager-store@数据管理

**自动化构架Vuex**

1. **main.js** 引入初始化store

```js
  import store  from './store'
  import {StoreManager}  from 'ab-manager-store'
  StoreManager.init(store)
```

**store.js**（例）

```js
  import Vue from 'vue'
  import Vuex from 'vuex'
  Vue.use(Vuex)

  const store = new Vuex.Store({
    state() {
      return {
        currentTrade: '', // 打开的交易信息
      }
    },
    getters: {
      getCurrentTrade: (state) => {
        return state.currentTrade;
      }
    },
    mutations: {
      setCurrentTrade(state, tradeInfo) {
        state.currentTrade = tradeInfo;
      }
    }
  })
  export default store;
```

2. **交易页面**操作使用方法：

```js
  import {StoreManager} from "ab-manager-store";

  //dynamicDispatch方法 操作子模块
  StoreManager.dynamicDispatch(dynamicModuleName, type, name, arg)

  //dispatch 操作主状态库
  StoreManager.dispatch(type, name, arg)

  //clear 重置store状态
  StoreManager.clear()
```
3. **vuex.store**的缓存,在 **store.js** 引入
```js
  import {StoreBackup} from "ab-manager-store"
```

**store.js**（例）

```js
  import {StoreBackup} from "ab-manager-store"
  // 注册Store添加
  const store = new Vuex.Store({
    ...
    plugins: [StoreBackup]
  })
  // 默认将所有的state状态保存到localStorage
  // 要缓存某个state
  StoreBackup.watchSession(['addNum']) // 缓存到SessionStorage
  StoreBackup.watch(['addNum']) // 缓存到localStorage
  StoreBackup.onlySession(true) // 参数为true时，只能缓存到SessionStorage
```
> **StoreManager Events**

|事件名称|说明|参数|
|-----|:-----:|:------:|
|init|初始化Store|store:Vuex.store的实例|
|clear|重置store状态|不传参数: 重置所有store状态;</br>传一个参数：参数为某个子模块,则重置子模块的状态;  </br>参数为store某个状态的值,则重置这个状态的值</br>传两个值：第一个参数为子模块,</br>第二个参数模块的状态值,重置当前模块的状态值 |
|dispatch|操作主状态库|type, name, arg|
|dynamicDispatch|操作子模块的状态库|dynamicModuleName, type, name, arg|

> **dispatch Attributes**

|参数|说明|类型|可选值|
|-----|:-----:|:-----:|:-----:|
|type|操作状态的方法|string|states </br>getters </br>actions</br>mutations|
|name|状态的key或操作方法的函数名|string|-|
|arg|mutation/action操作的参数|*|-|

> **dynamicDispatch Attributes**

|参数|说明|类型|可选值|
|-----|:------:|:-----:|:-----:|
|dynamicModuleName|子模块名|string|-|
|type|操作状态的方法|string|states </br>getters </br>actions</br>mutations|
|name|子模块状态的key或操作方法的函数名|string|-|
|arg|mutation/action操作的参数|*|-|

> **StoreBackup Events**

|事件名称|说明|参数类型|
|-----|:-----:|:------:|
|watch|缓存到localStorage|array: 需要缓存的模块或者单个状态值</br>默认是缓存所有状态|
|watchSession|缓存到SessionStorage|array: 需要缓存的模块或者单个状态值</br>默认是缓存所有状态|
|onlySession|是否只能缓存到SessionStorage|boolean: true->只能缓存在SessionStorage;</br>false->默认值,SessionStorage、localStorage都可以缓存 |