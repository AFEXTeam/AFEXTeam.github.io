---
nav: zh-CN
---


### Expansion

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="http://192.9.200.185:50003/aui-m/#/component/expansion" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
  <div>
    <aui-expansion :hideOnBlur="false" v-model="expansion" tip="111">
      sss
      <div slot="content">
        <div v-for="i in 10" :key="i">{{i}}</div>
      </div>
    </aui-expansion>
  </div>
</template>

<script>
export default {
  data() {
    return {
      msg: "test",
      expansion: false
    };
  },
};
</script>
```


#### Github Issue