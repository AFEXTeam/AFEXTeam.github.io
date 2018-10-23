---
nav: zh-CN
---


### Radio

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="http://192.9.200.185:50003/aui-m/#/component/radio" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
  <div>
    <aui-group title="default">
      <aui-radio :options="radio001" @change="change"></aui-radio>
    </aui-group>
  
    <aui-group :title="$t('pre-select China(disabled)')">
      <aui-radio :options="radio001" value="China" disabled></aui-radio>
    </aui-group>
  
    <aui-group :title="'fill mode value is '+radio001Value">
      <aui-radio :selected-label-style="{color: '#FF9900'}" fill-mode :options="radio001" v-model="radio001Value" @change="change"></aui-radio>
    </aui-group>
  
    <aui-group title="fill mode with custom placeholder and label">
      <aui-radio fill-mode fill-label="Other" fill-placeholder="填写其他的哦" :options="radio001" @change="change"></aui-radio>
    </aui-group>
  
    <aui-group title="object options">
      <aui-radio fill-mode fill-label="Other" fill-placeholder="other" :options="radio003" @change="change"></aui-radio>
    </aui-group>
  
    <aui-group title="slot:each-item">
      <aui-radio :options="radio001">
        <template slot-scope="props" slot="each-item">
          <p>
            V{{ props }}
            <img src="http://dn-placeholder.qbox.me/110x110/FF2D55/000" class="aui-radio-icon"> {{ props.label }}
          </p>
        </template>
      </aui-radio>
    </aui-group>
  </div>
</template>



<script>

export default {
  data() {
    return {
      radio001: ['China', 'Japan'],
      radio001Value: 'China',
      radio002Value: 'Japan',
      radio003: [{
        icon: 'http://dn-placeholder.qbox.me/110x110/FF2D55/000',
        key: '001',
        value: 'radio001'
      }, {
        icon: 'http://dn-placeholder.qbox.me/110x110/FF2D55/000',
        key: '002',
        value: 'radio002'
      }]
    }
  },
  methods: {
    change(value, label) {
      console.log('change:', value, label)
    }
  }
}
</script>

```


#### Github Issue