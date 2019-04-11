# ab-manager-error-handler@错误处理

收集所有错误信息并处理。

1. 使用
```js
    // main.js
    import ErrorManager from 'ab-manager-error-handler'
    Vue.use(ErrorManager, {
        // callback可选，可以再后续通过方法重新设置
        callback: function(res) {
            /*
             * res.stack - 错误堆栈信息
             * res.file - 发生错误的位置(文件或VueComponent)
             * res.message - 单行错误信息
             */
            // todo
        }
    });
```
2. 更新/设置callback：
```js
    // $updateErrorCb函数的参数为一个函数，成为新的回调函数
    this.$updateErrorCb(function(res) {
        // todo
    });
```

| 参数     | 类型 | 默认值 | 说明 |
| -------- | --- | --- | --- |
| callback(可选) | function | - | 错误发生时的回调函数 |