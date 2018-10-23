---
nav: zh-CN
---


### Tabbar

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="http://192.9.200.185:50003/aui-m/#/component/tabbar" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
  <div>
    <aui-group>
      <aui-cell is-link title="Simple" link="/component/tabbar-simple"></aui-cell>
      <aui-cell is-link title="Switch icons" link="/component/tabbar-icon"></aui-cell>
    </aui-group>
    <aui-tabbar>
      <aui-tabbar-item>
        <img slot="icon" src="../assets/demo/icon_nav_button.png">
        <span slot="label">Wechat</span>
      </aui-tabbar-item>
      <aui-tabbar-item show-dot>
        <img slot="icon" src="../assets/demo/icon_nav_msg.png">
        <span slot="label">Message</span>
      </aui-tabbar-item>
      <aui-tabbar-item selected link="/component/demo">
        <img slot="icon" src="../assets/demo/icon_nav_article.png">
        <span slot="label">Explore</span>
      </aui-tabbar-item>
      <aui-tabbar-item badge="2">
        <img slot="icon" src="../assets/demo/icon_nav_cell.png">
        <span slot="label">News</span>
      </aui-tabbar-item>
    </aui-tabbar>
  </div>
</template>

<script>

export default {
}
</script>

```


#### Github Issue