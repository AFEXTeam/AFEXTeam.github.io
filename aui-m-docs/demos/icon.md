<!-- ---
nav: zh-CN
--- -->


### Icon

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="https://afexteam.github.io/aui-m-demo/#/component/icon" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
  <div>
    <aui-box gap="10px 10px">
      <aui-icon type="success"></aui-icon>
      <aui-icon type="info"></aui-icon>
      <aui-icon type="info-circle"></aui-icon>
      <aui-icon type="warn"></aui-icon>
      <aui-icon type="waiting"></aui-icon>
      <aui-icon type="waiting-circle"></aui-icon>
      <aui-icon type="safe-success"></aui-icon>
      <aui-icon type="safe_warn"></aui-icon>
      <aui-icon type="success-circle"></aui-icon>
      <aui-icon type="success-no-circle"></aui-icon>
      <aui-icon type="circle"></aui-icon>
      <aui-icon type="download"></aui-icon>
      <aui-icon type="cancel"></aui-icon>
      <aui-icon type="search"></aui-icon>
      <aui-icon type="clear"></aui-icon>
      <br/>
      <aui-icon type="success" is-msg></aui-icon>
      <aui-icon type="info" is-msg></aui-icon>
      <aui-icon type="warn" is-msg></aui-icon>
      <aui-icon type="waiting" is-msg></aui-icon>
      <aui-icon type="safe_success" is-msg></aui-icon>
      <aui-icon type="safe_warn" is-msg></aui-icon>
    </aui-box>
  </div>
</template>

<script>

export default {
}
</script>
```


#### Github Issue