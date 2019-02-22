<!-- ---
nav: zh-CN
--- -->


### Card

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="https://afexteam.github.io/aui-m-demo/#/component/card" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
  <div>
    <aui-divider>simple card with header and content</aui-divider>
	   <aui-card header="我的钱包">
      <div slot="content" class="card-demo-flex card-demo-content01">
        <div class="aui-1px-l aui-1px-r">
          <span>1130</span>
          <br/>
          京豆
        </div>
        <div class="aui-1px-r">
          <span>15</span>
          <br/>
          京东券
        </div>
        <div class="aui-1px-r">
          <span>0</span>
          <br/>
          京东卡/E卡
        </div>
        <div>
          <span>88</span>
          <br/>
          七天待还
        </div>
      </div>
    </aui-card>

    <br>
    <aui-divider>with footer</aui-divider>
     <aui-card header='商品详情' footer="查看更多" footerLink='/component/panel'>
      <p slot="content" class="card-padding">custom content</p>
    </aui-card>

    <br>
    <aui-divider>use header slot and content slot</aui-divider>
    <aui-card>
      <img slot="header" src="http://placeholder.qiniudn.com/640x300" style="width:100%;display:block;">
      <div slot="content" class="card-padding">
        <p style="color:#999;font-size:12px;">Posted on January 21, 2015</p>
        <p style="font-size:14px;line-height:1.2;">Quisque eget vestibulum nulla. Quisque quis dui quis ex ultricies efficitur vitae non felis. Phasellus quis nibh hendrerit..</p>
      </div>
    </aui-card>
  </div>
</template>

<script>
export default {
}
</script>

<style scoped lang="less">
@import '../../theme-default/components/common/1px.less';

.card-demo-flex {
  display: flex;
}
.card-demo-content01 {
  padding: 10px 0;
}
.card-padding {
  padding: 15px;
}
.card-demo-flex > div {
  flex: 1;
  text-align: center;
  font-size: 12px;
}
.card-demo-flex span {
  color: #f74c31;
}
</style>

```


#### Github Issue