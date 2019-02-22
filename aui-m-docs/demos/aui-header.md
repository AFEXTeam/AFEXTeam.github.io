<!-- ---
nav: zh-CN
--- -->


### AuiHeader

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="https://afexteam.github.io/aui-m-demo/#/component/aui-header" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
  <div>
    <br>
    <aui-header backText='' :showBack="true"  title="This is the page." :showMore="true"></aui-header>
    <br>
    <aui-header title="use prop:title"></aui-header>
    <br>
    <aui-header :showBack="false">do not show Back</aui-header>
    <br>
    <aui-header backText= ''>set empty back text</aui-header>
    <br>
    <aui-header  @click-more="showMenus = true">with more menu</aui-header>
    <br>
    <aui-header>with right link
      <a slot="right">Feedback</a>
    </aui-header>
    <br>
    <aui-header>long long long long long long long text
      <a slot="right">Feedback</a>
    </aui-header>
    <br>
    <aui-header>with left slot
      <a slot="left">Close</a>
    </aui-header>
    <br>
    <aui-header>
      <span>overwrite-left</span>
      <aui-icon slot="overwrite-left" type="navicon" size="35" style="fill:#fff;position:relative;top:-8px;left:-3px;"></aui-icon>
    </aui-header>
    <br>
    <aui-header style="background-color:#000;">custom background color</aui-header>
    <br>
    <aui-header title="slot:overwrite-title">
      <div class="overwrite-title-demo" slot="overwrite-title">
        <aui-button-tab>
          <aui-button-tab-item selected>A</aui-button-tab-item>
          <aui-button-tab-item >B</aui-button-tab-item>
        </aui-button-tab>
      </div>
    </aui-header>
    <div v-transfer-dom>
      <aui-actionsheet :menus="menus" v-model="showMenus" show-cancel></aui-actionsheet>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      menus: {
        menu1: 'Take Photo',
        menu2: 'Choose from photos'
      },
      showMenus: false
    }
  }
}
</script>
<style>
.overwrite-title-demo {
  margin-top: 5px;
}
</style>
```


#### Github Issue