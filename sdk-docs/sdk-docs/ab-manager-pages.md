# ab-manager-pages@页面管理

对交易页面进行管理。

1.引入

```js
    // main.js

    import { PageManager } from 'ab-manager-pages'
    import Pages from '@/pages.js' // 此位置为pages.js的相对路径
    Vue.use(PageManager, { pages: Pages })
```

创建`page.js`文件：

```js
    // page.js

    export default [
        {
            name: stepName,
            page: url
        }
    ]
```

`page.js`(例)
```js
    // page.js

    export default [
        {
            name: 'Step1',
            page: 'FCClient/modules/T10001/Step1.vue'
        },
        {
            name: 'Step2',
            page: 'FCClient/modules/T10001/Step2.vue'
        }
    ]
```

> PageManager Events

|事件名|说明|参数|
|-----|:-----:|:-----:|
|getPage|获取页面的路径|name: page.js声明的每个页面的name值|

> page.js 声明参数的含义

| 参数     | 类型 | 说明 |
| -------- | :---: | :---: |
| stepName | string | 打开页面的名字 |
| chunkName | string | 工程打包之后的标示，不同的chunkName会分别打出一个文件 |
| url | string | 对应的Vue页面路径 |
