---
nav: zh-CN
---


### AuiDialog

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="http://192.9.200.185:50003/aui-m/#/component/aui-dialog" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
  <div style="height: 1000px">
  
    <aui-group>
      <aui-switch v-model="show" :title="$t('Toggle')"></aui-switch>
      <aui-switch v-model="show2" :title="$t('use .sync')"></aui-switch>
      <aui-switch v-model="showToast" :title="$t('show toast')"></aui-switch>
      <aui-switch v-model="showHideOnBlur" :title="$t('hide on clicking mask')"></aui-switch>
      <aui-switch v-model="showDialogStyle" :title="$t('Toggle')" :inline-desc="$t('custom dialog style')"></aui-switch>
    </aui-group>
  
    <div v-transfer-dom>
      <aui-dialog v-model="showToast" class="dialog-demo">
        <div style="padding:15px;">
          <aui-button @click.native="doShowToast" type="primary">show toast</aui-button>
        </div>
        <div @click="showToast=false">
          <span class="aui-close"></span>
        </div>
      </aui-dialog>
    </div>
  
    <div v-transfer-dom>
      <aui-dialog v-model="show" class="dialog-demo">
        <div class="img-box">
          <img src="../assets/demo/dialog/01.jpg" style="max-width:100%">
        </div>
        <div @click="show=false">
          <span class="aui-close"></span>
        </div>
      </aui-dialog>
    </div>
  
    <div v-transfer-dom>
      <aui-dialog :show.sync="show2" class="dialog-demo">
        <div class="img-box">
          <img src="../assets/demo/dialog/01.jpg" style="max-width:100%">
        </div>
        <div @click="show2=false">
          <span class="aui-close"></span>
        </div>
      </aui-dialog>
    </div>
  
    <div v-transfer-dom>
      <aui-dialog v-model="showHideOnBlur" class="dialog-demo" hide-on-blur>
        <div class="img-box">
          <img src="../assets/demo/dialog/01.jpg" style="max-width:100%">
        </div>
        <div @click="showHideOnBlur=false">
          <span class="aui-close"></span>
        </div>
      </aui-dialog>
    </div>
  
    <div v-transfer-dom>
      <aui-dialog v-model="showDialogStyle" hide-on-blur :dialog-style="{'max-width': '100%', width: '100%', height: '50%', 'background-color': 'transparent'}">
        <p style="color:#fff;text-align:center;" @click="showDialogStyle = false">
          <span style="font-size:30px;">HELLO WORLD</span>
          <br>
          <br>
          <aui-icon type="ios-close-outline" style="fill:#fff;"></aui-icon>
        </p>
      </aui-dialog>
    </div>
  
    <aui-group style="padding-top: 300px">
      <aui-switch v-model="showScrollBox" :title="$t('long long content')"></aui-switch>
    </aui-group>
  
    <div v-transfer-dom>
      <aui-dialog v-model="showScrollBox" class="dialog-demo">
        <p class="dialog-title">Long content</p>
        <div class="img-box" style="height:100px;padding:15px 0;overflow:scroll;-webkit-overflow-scrolling:touch;">
          <p v-for="i in 20">{{i}}</p>
        </div>
        <div @click="showScrollBox=false">
          <span class="aui-close"></span>
        </div>
      </aui-dialog>
    </div>
  
  </div>
</template>



<script>
export default {
  data() {
    return {
      show: false,
      show2: false,
      showHideOnBlur: false,
      showScrollBox: false,
      showDialogStyle: false,
      showToast: false
    }
  },
  methods: {
    doShowToast() {
      this.$aui.toast.show({
        text: 'toast'
      })
    }
  },
}
</script>

<style lang="less" scoped>
@import '../../theme-default/components/common/close';

.dialog-demo {
  .aui-dialog {
    border-radius: 8px;
    padding-bottom: 8px;
  }
  .dialog-title {
    line-height: 30px;
    color: #666;
  }
  .img-box {
    height: 350px;
    overflow: hidden;
  }
  .aui-close {
    margin-top: 8px;
    margin-bottom: 8px;
  }
}
</style>

```


#### Github Issue