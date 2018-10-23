---
nav: zh-CN
---


### ColorPicker

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="http://192.9.200.185:50003/aui-m/#/component/color-picker" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
  <div>
    <div style="padding: 15px;">
      <aui-color-picker :colors="colors1" v-model="color1"></aui-color-picker>
      <br>
      <aui-color-picker :colors="colors1" v-model="color1" size="middle"></aui-color-picker>
    </div>
    <aui-group title="as a cell's content">
      <aui-cell :title="'Color:' + color1">
        <aui-color-picker  :colors="colors1" v-model="color1" size="small"></aui-color-picker>
      </aui-cell>
    </aui-group>
    <aui-group title="a cell without title">
      <aui-cell primary="content">
        <aui-color-picker :colors="colors1" v-model="color1" size="middle"></aui-color-picker>
      </aui-cell>
    </aui-group>
  </div>
</template>

<script>


export default {
  data () {
    return {
      color1: '#FFEF7D',
      colors1: ['#FF3B3B', '#FFEF7D', '#8AEEB1', '#8B8AEE', '#CC68F8', '#fff']
    }
  }
}
</script>

```


#### Github Issue