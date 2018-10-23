---
nav: zh-CN
---


### Flexbox

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="http://192.9.200.185:50003/aui-m/#/component/flexbox" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
  <div>
    <aui-divider>Horizontal</aui-divider>
    <aui-flexbox>
      <aui-flexbox-item><div class="flex-demo">1</div></aui-flexbox-item>
      <aui-flexbox-item><div class="flex-demo">2</div></aui-flexbox-item>
    </aui-flexbox>
    <br>
    <aui-flexbox>
      <aui-flexbox-item><div class="flex-demo">1</div></aui-flexbox-item>
      <aui-flexbox-item><div class="flex-demo">2</div></aui-flexbox-item>
      <aui-flexbox-item><div class="flex-demo">3</div></aui-flexbox-item>
    </aui-flexbox>
    <br>
    <aui-flexbox>
      <aui-flexbox-item><div class="flex-demo">1</div></aui-flexbox-item>
      <aui-flexbox-item><div class="flex-demo">2</div></aui-flexbox-item>
      <aui-flexbox-item><div class="flex-demo">3</div></aui-flexbox-item>
      <aui-flexbox-item><div class="flex-demo">4</div></aui-flexbox-item>
    </aui-flexbox>
    <br>
    <aui-flexbox>
      <aui-flexbox-item><div class="flex-demo">1</div></aui-flexbox-item>
      <aui-flexbox-item><div class="flex-demo">2</div></aui-flexbox-item>
      <aui-flexbox-item><div class="flex-demo">3</div></aui-flexbox-item>
      <aui-flexbox-item><div class="flex-demo">4</div></aui-flexbox-item>
      <aui-flexbox-item><div class="flex-demo">5</div></aui-flexbox-item>
    </aui-flexbox>
    <br>
    <aui-flexbox>
      <aui-flexbox-item><div class="flex-demo">1</div></aui-flexbox-item>
      <aui-flexbox-item><div class="flex-demo">2</div></aui-flexbox-item>
      <aui-flexbox-item><div class="flex-demo">3</div></aui-flexbox-item>
      <aui-flexbox-item><div class="flex-demo">4</div></aui-flexbox-item>
      <aui-flexbox-item><div class="flex-demo">5</div></aui-flexbox-item>
      <aui-flexbox-item><div class="flex-demo">6</div></aui-flexbox-item>
    </aui-flexbox>
    <br>
    <aui-divider>Honrizontal with no gutter</aui-divider>
    <aui-flexbox :gutter="0">
      <aui-flexbox-item><div class="flex-demo">1</div></aui-flexbox-item>
      <aui-flexbox-item><div class="flex-demo">2</div></aui-flexbox-item>
      <aui-flexbox-item><div class="flex-demo">3</div></aui-flexbox-item>
      <aui-flexbox-item><div class="flex-demo">4</div></aui-flexbox-item>
    </aui-flexbox>
    <br>
    <aui-divider>Vertical</aui-divider>
    <aui-flexbox orient="vertical">
      <aui-flexbox-item><div class="flex-demo">1</div></aui-flexbox-item>
      <aui-flexbox-item><div class="flex-demo">2</div></aui-flexbox-item>
    </aui-flexbox>
    <br>
    <aui-divider>Vertical with no gutter</aui-divider>
    <aui-flexbox orient="vertical" :gutter="0">
      <aui-flexbox-item><div class="flex-demo">1</div></aui-flexbox-item>
      <aui-flexbox-item><div class="flex-demo">2</div></aui-flexbox-item>
    </aui-flexbox>
    <br>
    <aui-divider>Grid support(12 columns)</aui-divider>
    <aui-flexbox>
      <aui-flexbox-item :span="4"><div class="flex-demo">1/3</div></aui-flexbox-item>
      <aui-flexbox-item><div class="flex-demo">2/3</div></aui-flexbox-item>
    </aui-flexbox>
    <br>
    <aui-flexbox>
      <aui-flexbox-item :span="6"><div class="flex-demo">6/12</div></aui-flexbox-item>
      <aui-flexbox-item :span="2"><div class="flex-demo">2/12</div></aui-flexbox-item>
      <aui-flexbox-item ><div class="flex-demo">rest</div></aui-flexbox-item>
    </aui-flexbox>
    <br>
    <aui-divider>flexiable grid</aui-divider>
    <aui-flexbox>
      <aui-flexbox-item :span="1/3"><div class="flex-demo">1/3</div></aui-flexbox-item>
      <aui-flexbox-item :span="1/6"><div class="flex-demo">1/6</div></aui-flexbox-item>
      <aui-flexbox-item :span="1/8"><div class="flex-demo">1/8</div></aui-flexbox-item>
      <aui-flexbox-item :span="1/8"><div class="flex-demo">1/8</div></aui-flexbox-item>
      <aui-flexbox-item><div class="flex-demo">rest</div></aui-flexbox-item>
    </aui-flexbox>
    <br>
    <aui-flexbox :gutter="0">
      <aui-flexbox-item :span="1/3"><div class="flex-demo">1/3</div></aui-flexbox-item>
      <aui-flexbox-item :span="1/6"><div class="flex-demo">1/6</div></aui-flexbox-item>
      <aui-flexbox-item :span="1/8"><div class="flex-demo">1/8</div></aui-flexbox-item>
      <aui-flexbox-item :span="1/8"><div class="flex-demo">1/8</div></aui-flexbox-item>
      <aui-flexbox-item><div class="flex-demo">rest</div></aui-flexbox-item>
    </aui-flexbox>
    <br>
    <aui-divider>flexiable grid</aui-divider>
    <aui-flexbox :gutter="0">
      <aui-flexbox-item :span="1/3" :order="4"><div class="flex-demo">1</div></aui-flexbox-item>
      <aui-flexbox-item :span="1/6" :order="3"><div class="flex-demo">2</div></aui-flexbox-item>
      <aui-flexbox-item :span="1/8" :order="2"><div class="flex-demo">3</div></aui-flexbox-item>
      <aui-flexbox-item :span="1/8" :order="1"><div class="flex-demo">4</div></aui-flexbox-item>
      <aui-flexbox-item :order="-99"><div class="flex-demo">5</div></aui-flexbox-item>
    </aui-flexbox>
    <br>
    <aui-divider>flex-wrap</aui-divider>
    <aui-flexbox :gutter="0" wrap="wrap">
      <aui-flexbox-item :span="1/3"><div class="flex-demo">1/3</div></aui-flexbox-item>
      <aui-flexbox-item :span="1/3"><div class="flex-demo">1/3</div></aui-flexbox-item>
      <aui-flexbox-item :span="1/3"><div class="flex-demo">1/3</div></aui-flexbox-item>
      <aui-flexbox-item :span="1/3"><div class="flex-demo">1/3</div></aui-flexbox-item>
      <aui-flexbox-item :span="1/3"><div class="flex-demo">1/3</div></aui-flexbox-item>
      <aui-flexbox-item :span="1/3"><div class="flex-demo">1/3</div></aui-flexbox-item>
      <aui-flexbox-item :span="1/3"><div class="flex-demo">1/3</div></aui-flexbox-item>
      <aui-flexbox-item :span="1/3"><div class="flex-demo">1/3</div></aui-flexbox-item>
    </aui-flexbox>
    
  </div>
</template>

<script>

export default {
}
</script>

<style lang="less">
@import '../../theme-default/components/common/1px.less';

.flex-demo {
  text-align: center;
  color: #fff;
  background-color: #20b907;
  border-radius: 4px;
  background-clip: padding-box;
}
</style>

```


#### Github Issue