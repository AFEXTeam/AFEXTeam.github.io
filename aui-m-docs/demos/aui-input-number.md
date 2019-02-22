<!-- ---
nav: zh-CN
--- -->


### AuiInputNumber

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="https://afexteam.github.io/aui-m-demo/#/component/aui-input-number" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
  <div>
    <aui-group :title="$t('Default')">
      <aui-input-number :name="$t('Quantity')" :title="$t('Quantity')"></aui-input-number>
    </aui-group>

    <aui-group :title="$t('listen')">
      <aui-input-number :title="$t('Quantity')" :value="0" :min="0" @change="change"></aui-input-number>
    </aui-group>

    <aui-group :title="$t('set width=100px')">
      <aui-input-number :title="$t('Quantity')" width="100px"></aui-input-number>
    </aui-group>

    <aui-group :title="$t('round style')">
      <aui-input-number :title="$t('Quantity')" v-model="roundValue" button-style="round" :min="0" :max="5"></aui-input-number>
    </aui-group>

    <aui-group :title="$t('set step=0.5')">
      <aui-input-number :title="$t('Quantity')" :step="0.5"></aui-input-number>
    </aui-group>

    <aui-group :title="$t('set value=1, min=-5 and max=8')">
      <aui-input-number :title="$t('Quantity')" :min="-5" :max="8" :value="1"></aui-input-number>
    </aui-group>

    <aui-group :title="$t('fillable = true')">
      <aui-input-number :value="10" :title="$t('Quantity')" fillable></aui-input-number>
    </aui-group>

  </div>
</template>



<script>
export default {

  data () {
    return {
      roundValue: 1
    }
  },
  methods: {
    change (val) {
      console.log('change', val)
    }
  }
}
</script>

```


#### Github Issue