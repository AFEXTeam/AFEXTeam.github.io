---
nav: zh-CN
---


### AuiSwitch

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="http://192.9.200.185:50003/aui-m/#/component/aui-switch" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
  <div>
    <aui-group :title="$t('value map')">
      <aui-switch :title="$t('default true')" :value-map="['0', '1']" v-model="stringValue"></aui-switch>
      <aui-cell title="value" :value="typeof stringValue + ' ' + stringValue"></aui-cell>
    </aui-group>
    <aui-group :title="$t('Basic Usage')">
      <aui-switch :title="$t('default false')"></aui-switch>
      <aui-switch :title="$t('default true')" :inline-desc="value1 + ''" v-model="value1"></aui-switch>
    </aui-group>
    <aui-group :title="$t('disabled')">
      <aui-switch :title="$t('default false')" disabled></aui-switch>
      <aui-switch :title="$t('default true')" :value="true" disabled></aui-switch>
    </aui-group>
    <aui-group :title="$t('prevent default')">
      <aui-switch :title="$t('default false')" prevent-default v-model="value2" @click="onClick"></aui-switch>
    </aui-group>
    <aui-group :title="$t('html title')">
      <aui-switch disabled :title="$t('switch red')"></aui-switch>
    </aui-group>
  </div>
</template>



<script>

export default {
  methods: {
    onClick(newVal, oldVal) {
      console.log(newVal, oldVal)
      this.$aui.loading.show({
        text: 'in processing'
      })
      setTimeout(() => {
        this.$aui.loading.hide()
        this.value2 = newVal
      }, 1000)
    }
  },
  data() {
    return {
      value1: true,
      value2: false,
      stringValue: '0'
    }
  }
}
</script>

```


#### Github Issue