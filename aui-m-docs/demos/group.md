---
nav: zh-CN
---


### Group

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="http://192.9.200.185:50003/aui-m/#/component/group" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
  <div>
    <aui-group label-width="4.5em" label-margin-right="2em" label-align="right">
      <aui-cell title="Cell" value="value" is-link></aui-cell>
      <aui-cell title="Cell" value="value" is-link value-align="left"></aui-cell>
      <aui-input title="上报人" v-model="value1"></aui-input>
      <aui-input placeholder="I'm placeholder">
        <img slot="restricted-label" style="display:inline-block;vertical-align:middle;" src="http://dn-placeholder.qbox.me/110x110/FF2D55/000" width="24" height="24">
      </aui-input>
      <aui-input title="上<i class='aui-blank-half'></i>报<i class='aui-blank-half'></i>人" v-model="value1"></aui-input>
      <aui-input-number title="Quantity" align="left" v-model="numberValue" button-style="round" :min="0" :max="5"></aui-input-number>
      <aui-datetime title="时&emsp;&emsp;&nbsp;间" v-model="time1" value-text-align="left"></aui-datetime>
      <aui-selector title="隐患类别" :options="['工艺技术', '其他']" v-model="value2"></aui-selector>
      <aui-selector title="隐患类别" placeholder="Placeholder" :options="['工艺技术', '其他']" v-model="value7"></aui-selector>
      <aui-selector title="隐患类别" :options="['工艺技术', '其他']" v-model="value8"></aui-selector>
      <aui-input title="隐患部位" placeholder="必填" v-model="value3"></aui-input>
      <aui-input title="密码" type="password" placeholder="必填" v-model="value4"></aui-input>
      <aui-popup-picker title="请选择" :data="list" v-model="value5" value-text-align="left"></aui-popup-picker>
      <aui-popup-picker title="请选择" placeholder="Required" :data="list" v-model="value6" value-text-align="left"></aui-popup-picker>
      <!-- <aui-address title="地址选择" v-model="addressValue" raw-value :list="addressData" value-text-align="left"></aui-address> -->
      <aui-textarea title="详细信息" placeholder="请填写详细信息" :show-counter="false" :rows="3"></aui-textarea>
      <aui-textarea placeholder="请填写详细信息" :show-counter="false" :rows="3">
        <img slot="restricted-label" style="display:inline-block;vertical-align:middle;" src="http://dn-placeholder.qbox.me/110x110/FF2D55/000" width="24" height="24">
      </aui-textarea>
    </aui-group>
    <br>
    <aui-group>
      <aui-group-title slot="title">I'm a title
        <span style="float:right;">right</span>
      </aui-group-title>
      <aui-cell title="cell"></aui-cell>
    </aui-group>
    <br>
    <aui-group title="justify" label-width="5.5em" label-margin-right="2em" label-align="justify">
      <aui-cell title="哈哈" value="value" is-link></aui-cell>
      <aui-cell title="哈哈哈哈哈" value="value" is-link value-align="left"></aui-cell>
      <aui-input title="上报人" v-model="value1"></aui-input>
      <aui-input-number title="Quantity" align="left" v-model="numberValue" button-style="round" :min="0" :max="5"></aui-input-number>
      <aui-datetime title="时间" v-model="time1" value-text-align="left"></aui-datetime>
      <aui-selector title="隐患类别" :options="['工艺技术', '其他']" v-model="value2"></aui-selector>
      <aui-popup-picker title="请选择" :data="list" v-model="value5" value-text-align="left"></aui-popup-picker>
      <!-- <aui-address title="地址选择" v-model="addressValue" raw-value :list="addressData" value-text-align="left" label-align="justify"></aui-address> -->
      <aui-switch title="选择"></aui-switch>
      <aui-textarea title="详细信息" placeholder="请填写详细信息" :show-counter="false" :rows="3"></aui-textarea>
    </aui-group>
    <br>
  </div>
</template>

<script>
import {ChinaAddressData} from '../../src/utils'
export default {
  data() {
    return {
      addressData: ChinaAddressData,
      addressValue: ['广东省', '深圳市', '南山区'],
      value1: '张三',
      value2: '工艺技术',
      value3: '',
      value7: '',
      value8: '',
      value4: '',
      time1: '2017-06-01',
      value5: ['A'],
      value6: [],
      list: [['A', 'B', 'C']],
      numberValue: 0
    }
  }
}
</script>

```


#### Github Issue