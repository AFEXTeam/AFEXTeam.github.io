# 工程结构文档

-----
```js
|—— ab-manager ~manager插件
|   |—— ab-manager-focus
|   |—— ab-manager-store
|   |—— ...
|—— agree-sdk ~移动sdk插件
|   |—— index.js
|—— aui-m ~移动组件库
|—— build ~webpack文件
|—— config ~webpack配置
|—— dist ~打包后工程所在的文件夹
|—— src ~工程的源码
|   |—— activity ~存放主工程的相关vue文件
|   |   |—— Login.vue
|   |   |—— Home.vue
|   |   |—— ...
|   |—— common ~多个文件同时会使用的，通用的js文件
|   |   |—— mixin ~混合的公共js文件 
|   |   |   |—— ...
|   |   |—— manager
|	|   |   |—— services-manager ~服务的配置
|   |   |   | 	|—— services-error.js
|	|   |   |   |—— services-names.js
|	|   |   |   |—— services-plugin.js
|	|   |   |—— ...
|   |   |—— utils ~工具类js
|   |   |   |—— md5.js
|   |   |   |—— ...
|   |   |—— ...
|   |—— components ~复用的组件模板
|   |   |—— MyTable.vue
|   |   |—— ValidateTemplate.vue
|   |   |—— ...
|   |—— modules ~多页的子页工程目录
|   |   |—— t1001 ~切换页面建议通过动态组件
|   |   |   |—— App.vue
|   |   |   |—— main.js
|   |   |   |—— index.html
|   |   |—— ...
|   |—— App.vue ~主工程入口
|   |—— main.js ~主工程全局配置
|   |—— router ~主工程路由
|	|——index.js
|   |—— store.js ~主工程的vuex存储文件
|—— static ~静态资源，不参与工程打包
|   |—— locales ~语言文件包
|   |   |—— aui-lang ~组件库语言文件包
|   |   |   |—— en.js
|   |   |   |—— zh-cn.js
|   |   |   |—— zh-tw.js
|   |   |—— en.js
|   |   |—— zh-cn.js
|   |   |—— zh-tw.js
|   |—— config.js ~语言和主机地址的配置
|   |—— images ~图片文件
```
