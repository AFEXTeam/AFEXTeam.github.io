---
nav: zh-CN
---


### Spinner

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="http://192.9.200.185:50003/aui-m/#/component/spinner" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
  <div>
    <aui-group>
      <aui-cell v-for="(type, index) in types"
            :title="type"
            :key="type"
            :inline-desc="index === 3 ? 'size=40px' : ''">
        <aui-spinner :type="type"
                 :size="index === 3 ? 40 : 28"></aui-spinner>
      </aui-cell>
    </aui-group>
  </div>
</template>

<script>

export default {
  data() {
    return {
      types: ['android', 'ios', 'ios-small', 'bubbles', 'circles', 'crescent', 'dots', 'lines', 'ripple', 'spiral']
    }
  }
}
</script>

```


#### Github Issue