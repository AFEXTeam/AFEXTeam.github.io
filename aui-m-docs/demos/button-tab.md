<!-- ---
nav: zh-CN
--- -->


### ButtonTab

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="https://afexteam.github.io/aui-m-demo/#/component/button-tab" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
  <div>
    <div style="padding: 15px;">
      <aui-button-tab>
        <aui-button-tab-item>{{ $t('Today') }}</aui-button-tab-item>
        <aui-button-tab-item selected>{{ $t('This Week') }}</aui-button-tab-item>
        <aui-button-tab-item>{{ $t('This Month') }}</aui-button-tab-item>
      </aui-button-tab>      
      <br>
      <aui-divider>{{ $t('Use v-model to set selected item') }}</aui-divider>
      <br>
      <aui-button-tab v-model="demo01">
        <aui-button-tab-item @item-click="consoleIndex()">{{ $t('Articles') }}</aui-button-tab-item>
        <aui-button-tab-item @item-click="consoleIndex()">{{ $t('Products') }}</aui-button-tab-item>
      </aui-button-tab>
      <br>
      <aui-button-tab v-model="demo01">
        <aui-button-tab-item>{{ $t('Articles sync') }}</aui-button-tab-item>
        <aui-button-tab-item>{{ $t('Products sync') }}</aui-button-tab-item>
      </aui-button-tab>
      <br>
      <aui-divider>{{ $t('Red Dot') }}</aui-divider>
      <br>
      <aui-button-tab>
        <aui-button-tab-item selected>{{ $t('All Messages') }}</aui-button-tab-item>
        <aui-button-tab-item><span class="aui-reddot-s">{{ $t('New Messages') }}</span></aui-button-tab-item>
      </aui-button-tab>
    </div>
  </div>
</template>



<script>
export default {
  methods: {
    consoleIndex () {
      console.log('click demo01', this.demo01)
    }
  },
  data () {
    return {
      demo01: 0
    }
  }
}
</script>

```


#### Github Issue