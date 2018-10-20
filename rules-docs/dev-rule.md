#前端开发规范

----

## 一、通用规范

### 1.统一采用四格缩进

### 2.尽量使用`let`声明变量，不要用`var`

### 3.复杂代码必须添加注释

### 4.声明变量、方法名和类名等必须见名知意

### 5.嵌套节点必须使用缩进

### 6.html编码方式采用UTF-8

### 7.vue文件`<template>`中不要直接使用内联样式

### 8.vue文件`<style>`标签中使用`scoped`

如遇不可覆盖样式，可采用以下方法：
```
.aui-col >>> .aui-button--primary {
	/* custom style */
}
```

### 9.vue文件的`export default {}`上面注明该文件用途

###10.vue文件中的方法，不需要写`function`关键字，采用如下方式声明或箭头函数
```
doSomthing() {
	// todo
}
```

###11.`changelog`文件最新改动写在在最上面

## 二、命名规范

### 1.文件夹命名
    全小写，短横线命名法（kebab-case），如：home 或 my-folder

### 2.html文件
  	 全小写， 短横线命名法（kebab-case），如：index.html 或 index-log.html

### 3.css文件(scss|less)
    全小写，短横线命名法（kebab-case），如：var.css 或 app-common.css

### 4.js文件(ts|tsx|jsx)
    全小写，短横线命名法（kebab-case），如：utils.js 或 my-utils.js

### 5.vue文件
    帕斯卡命名法（Pascal），即“大驼峰”，如：Login.vue 或 HomeContainer.vue

### 6.json文件
    下划线命名法（kebab-case），如：package.json 或 my-config.json

### 7.md文件
    全小写，短横线命名法（kebab-case），如：rule.md 或 rule-ios.md

> 仅README.md采用全大写形式。

### 8.图片文件
	全小写，短横线命名法（kebab-case），如：avatar.png 或 my-logo.png

### 9. html相关

#### 9-1.属性名
	全小写，短横线命名法（kebab-case），全小写，如：type 或 data-name

### 10.css相关

#### 10-1.id命名
    采用驼峰命名（camelCase），即“小驼峰”，如：id="myApp"
#### 10-2.class命名
    全小写，短横线命名法（kebab-case），如：class = "home home-dashboard"

> **注：**严禁在标签上直接写`style`之类的内联样式。

### 11.js相关

#### 11-1.变量
    采用驼峰命名（camelCase），如：let name 或 let userName

#### 11-2.常量
    全大写，下划线命名法，如：GLOBAL 或 MAX_COUNT

#### 11-3.方法名
    采用驼峰命名（camelCase），即“小驼峰”，如：function doSomthing() {}

#### 11-4.类名
    帕斯卡命名法（Pascal），即“大驼峰”，如：class User {}

### 12.vue相关

#### 12-1.变量命名
    同js变量命名

#### 12-2.常量命名
    同js常量命名

#### 12-3.方法命名
    同js方法命名

#### 12-6.name属性
    帕斯卡命名法（Pascal），如：name: "CustomComponent"