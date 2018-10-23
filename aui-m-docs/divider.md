---
nav: zh-CN
---


### Divider

<img width="100" src="http://qr.topscan.com/api.php?text=https%3A%2F%2Fvux.li%2Fdemos%2Fv2%2F%23%2Fcomponent%2Fdivider"/>

<a href="https://vux.li/demos/v2/#/component/divider" target="_blank" style="font-size:12px;color:#888;">demo 原始链接：https://vux.li/demos/v2/#/component/divider</a>


#### 交互&设计参考

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="https://vux.li/demos/v2/#/component/divider" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
<div>
  <divider>{{ $t('I have bottom line') }}</divider>
</div>
</template>



<script>
import { Divider } from 'vux'

export default {
  components: {
    Divider
  }
}
</script>
```


#### Github Issue