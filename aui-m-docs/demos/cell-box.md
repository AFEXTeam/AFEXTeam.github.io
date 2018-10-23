---
nav: zh-CN
---


### CellBox

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="http://192.9.200.185:50003/aui-m/#/component/cell-box" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
  <div>
    <aui-group>
      <aui-cell title="cell" value="hello" is-link></aui-cell>
      <aui-cell-box link="/demo" :is-link='false'>
        cell-box long long long long long long long
      </aui-cell-box>
      <aui-cell-box>
        cell-box hello world hello world hello world
      </aui-cell-box>
      <aui-cell title="cell" value="hello" is-link></aui-cell>
    </aui-group>
  </div>
</template>

<script>

export default {
}
</script>
```


#### Github Issue